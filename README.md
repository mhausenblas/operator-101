# Extending Kubernetes 101 demos

## kubectl plugin

I have a plugin called `inspect` that renders a resources in YAML:

```
$ kubectl plugin list
The following kubectl-compatible plugins are available:

/Users/mhausenblas/bin/kubectl-inspect

$ cat /Users/mhausenblas/bin/kubectl-inspect
#!/bin/bash
kubectl get "$@" -o yaml | bat -l yaml -p

$ kubectl inspect svc/kubernetes
apiVersion: v1
kind: Service
metadata:
  creationTimestamp: 2018-11-09T20:22:32Z
  labels:
    component: apiserver
    provider: kubernetes
  name: kubernetes
  namespace: default
  resourceVersion: "35"
  selfLink: /api/v1/namespaces/default/services/kubernetes
  uid: 2fd4175e-e45d-11e8-8911-ca17f3440361
spec:
  clusterIP: 10.96.0.1
  ports:
  - name: https
    port: 443
    protocol: TCP
    targetPort: 8443
  sessionAffinity: None
  type: ClusterIP
status:
  loadBalancer: {}
```

## Operator

Using the [Operator SDK](https://github.com/operator-framework/operator-sdk). 
See also docs:

- [CLI reference](https://github.com/operator-framework/operator-sdk/blob/master/doc/sdk-cli-reference.md)
- [User Guide](https://github.com/operator-framework/operator-sdk/blob/master/doc/user-guide.md)

### Bootstrapping operator

All the business goes on in a dedicated namespace:

```
$ kubectl create ns ndp-demo
```

STEP 1—preparation:

```
$ cd $GOPATH/src/github.com/mhausenblas
$ operator-sdk new nodefpol-operator
$ cd nodefpol-operator
```

See also [terminal output](STEP-1_outputof_new_app-operator.md) of above command.

STEP 2—add a new API for the custom resource NoDefaultsPolicy:

```
$ pwd
/Users/mhausenblas/Dropbox/dev/work/src/github.com/mhausenblas/nodefpol-operator

$ operator-sdk add api --api-version=nodefpol.k8space.io/v1alpha1 --kind=NoDefaultsPolicy
```

See also [terminal output](STEP-2_outputof_add_api.md) of above command.

STEP 3—add a new controller that watches for NoDefaultsPolicy:

```
$ operator-sdk add controller --api-version=nodefpol.k8space.io/v1alpha1 --kind=NoDefaultsPolicy
```

See also [terminal output](STEP-3_outputof_add_controller.md) of above command.

### Local deployment

STEP 4—install CRD and launch the operator locally:

```
$ kubectl -n ndp-demo apply -f deploy/crds/nodefpol_v1alpha1_nodefaultspolicy_crd.yaml
$ OPERATOR_NAME=nodefpol-operator operator-sdk up local --namespace "ndp-demo"
```

See also [terminal output](STEP-4_outputof_operator-sdk-up.md) of above command.

Create a `NoDefaultsPolicy` custom resource (note that the default controller will watch for NoDefaultsPolicy objects for each CR):

```
$ kubectl -n ndp-demo apply -f deploy/crds/nodefpol_v1alpha1_nodefaultspolicy_cr.yaml
```

### In-cluster deployment

In order to deploy the operator into the cluster, we build a container image, push it to a registry,
and then create the necessary resources (SA, roles, CRD, etc.).

STEP 5—build and push the app-operator image to a public registry (note: make sure you're logged into registry, first):

```
$ operator-sdk build quay.io/mhausenblas/nodefpol
$ docker push quay.io/mhausenblas/nodefpol
```

Update the operator manifest to use the built image name:

```
$ sed -i "" 's|REPLACE_IMAGE|quay.io/mhausenblas/nodefpol|g' deploy/operator.yaml
```

STEP 6—set up service account, and  RBAC roles and bindings:

```
$ kubectl -n ndp-demo apply -f deploy/service_account.yaml
$ kubectl -n ndp-demo apply -f deploy/role.yaml
$ kubectl -n ndp-demo apply -f deploy/role_binding.yaml
```

STEP 7—set up the CRD (if not already done for local deployment):

```
$ kubectl -n ndp-demo apply -f deploy/crds/nodefpol_v1alpha1_nodefaultspolicy_crd.yaml
```

STEP 8—deploy the operator:

```
$ kubectl -n ndp-demo apply -f deploy/operator.yaml
```

STEP 9—create a `NoDefaultsPolicy` custom resource (if not already done for local deployment):

```
$ kubectl -n ndp-demo apply -f deploy/crds/nodefpol_v1alpha1_nodefaultspolicy_cr.yaml
```

To clean up:

```
$ kubectl delete ns ndp-demo
```

### Development

The Operator SDK creates a ton of boot-strapping code and config, however, now your work starts. To start this process, find `//TODO(user)` annotations in the Go source code and start implementing your custom logic.