```
$ OPERATOR_NAME=nodefpol-operator operator-sdk up local --namespace "ndp-demo"
2018/11/14 12:25:31 Go Version: go1.11.1
2018/11/14 12:25:31 Go OS/Arch: darwin/amd64
2018/11/14 12:25:31 operator-sdk Version: v0.1.1+git
2018/11/14 12:25:31 Registering Components.
2018/11/14 12:25:31 Starting the Cmd.

```

```
$ kubectl -n ndp-demo get crd
NAME                                     CREATED AT
nodefaultspolicies.nodefpol.k8space.io   2018-11-14T11:23:35Z

$ kubectl -n ndp-demo get NoDefaultsPolicy
NAME                       AGE
example-nodefaultspolicy   46s

$ kubectl -n ndp-demo describe NoDefaultsPolicy
Name:         example-nodefaultspolicy
Namespace:    ndp-demo
Labels:       <none>
Annotations:  kubectl.kubernetes.io/last-applied-configuration:
                {"apiVersion":"nodefpol.k8space.io/v1alpha1","kind":"NoDefaultsPolicy","metadata":{"annotations":{},"name":"example-nodefaultspolicy","nam...
API Version:  nodefpol.k8space.io/v1alpha1
Kind:         NoDefaultsPolicy
Metadata:
  Creation Timestamp:  2018-11-14T11:35:32Z
  Generation:          1
  Resource Version:    230729
  Self Link:           /apis/nodefpol.k8space.io/v1alpha1/namespaces/ndp-demo/nodefaultspolicies/example-nodefaultspolicy
  UID:                 651a1170-e801-11e8-87f9-ca17f3440361
Spec:
  Size:  3
Events:  <none>

$ kubectl -n ndp-demo get all
NAME                               READY   STATUS    RESTARTS   AGE
pod/example-nodefaultspolicy-pod   1/1     Running   0          5m
```