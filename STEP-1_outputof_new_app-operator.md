```
$ operator-sdk new app-operator
Create cmd/manager/main.go
Create build/Dockerfile
Create deploy/service_account.yaml
Create deploy/role.yaml
Create deploy/role_binding.yaml
Create deploy/operator.yaml
Create pkg/apis/apis.go
Create pkg/controller/controller.go
Create version/version.go
Create .gitignore
Create Gopkg.toml
Run dep ensure ...
Root project is "github.com/mhausenblas/nodefpol-operator/app-operator"
 4 transitively valid internal packages
 15 external packages imported from 6 projects
(0)   ✓ select (root)
(1)     ? attempt k8s.io/gengo with 1 pkgs; 1 versions to try
(1)         try k8s.io/gengo@master
(1)     ✓ select k8s.io/gengo@master w/5 pkgs
(2)     ? attempt github.com/spf13/pflag with 1 pkgs; 6 versions to try
(2)         try github.com/spf13/pflag@v1.0.3
(2)     ✓ select github.com/spf13/pflag@v1.0.3 w/1 pkgs
(3)     ? attempt k8s.io/klog with 1 pkgs; 11 versions to try
(3)         try k8s.io/klog@v0.1.0
(3)     ✓ select k8s.io/klog@v0.1.0 w/1 pkgs
(4)     ? attempt golang.org/x/tools with 1 pkgs; 11 versions to try
(4)         try golang.org/x/tools@master
(4)     ✓ select golang.org/x/tools@master w/4 pkgs
(5)     ? attempt github.com/operator-framework/operator-sdk with 2 pkgs; 13 versions to try
(5)         try github.com/operator-framework/operator-sdk@v0.1.1
(6)     ✗   github.com/operator-framework/operator-sdk@v0.1.1 not allowed by constraint master:
(6)         master from (root)
(5)         try github.com/operator-framework/operator-sdk@v0.1.0
(6)     ✗   github.com/operator-framework/operator-sdk@v0.1.0 not allowed by constraint master:
(6)         master from (root)
(5)         try github.com/operator-framework/operator-sdk@v0.0.7
(6)     ✗   github.com/operator-framework/operator-sdk@v0.0.7 not allowed by constraint master:
(6)         master from (root)
(5)         try github.com/operator-framework/operator-sdk@v0.0.6
(6)     ✗   github.com/operator-framework/operator-sdk@v0.0.6 not allowed by constraint master:
(6)         master from (root)
(5)         try github.com/operator-framework/operator-sdk@v0.0.5
(6)     ✗   github.com/operator-framework/operator-sdk@v0.0.5 not allowed by constraint master:
(6)         master from (root)
(5)         try github.com/operator-framework/operator-sdk@v0.0.4
(6)     ✗   github.com/operator-framework/operator-sdk@v0.0.4 not allowed by constraint master:
(6)         master from (root)
(5)         try github.com/operator-framework/operator-sdk@v0.0.3
(6)     ✗   github.com/operator-framework/operator-sdk@v0.0.3 not allowed by constraint master:
(6)         master from (root)
(5)         try github.com/operator-framework/operator-sdk@v0.0.2
(6)     ✗   github.com/operator-framework/operator-sdk@v0.0.2 not allowed by constraint master:
(6)         master from (root)
(5)         try github.com/operator-framework/operator-sdk@v0.0.1
(6)     ✗   github.com/operator-framework/operator-sdk@v0.0.1 not allowed by constraint master:
(6)         master from (root)
(5)         try github.com/operator-framework/operator-sdk@master
(5)     ✓ select github.com/operator-framework/operator-sdk@master w/2 pkgs
(6)     ? attempt k8s.io/api with 1 pkgs; 147 versions to try
(6)         try k8s.io/api@2d6f90ab1293a1fb871cf149423ebb72aa7423aa
(6)     ✓ select k8s.io/api@2d6f90ab1293a1fb871cf149423ebb72aa7423aa w/1 pkgs
(7)     ? attempt github.com/gogo/protobuf with 2 pkgs; 26 versions to try
(7)         try github.com/gogo/protobuf@v1.1.1
(7)     ✓ select github.com/gogo/protobuf@v1.1.1 w/2 pkgs
(8)     ? attempt sigs.k8s.io/controller-runtime with 3 pkgs; 13 versions to try
(8)         try sigs.k8s.io/controller-runtime@v0.1.7
(8)     ✓ select sigs.k8s.io/controller-runtime@v0.1.7 w/16 pkgs
(9)     ? revisit k8s.io/api to add 2 pkgs
(9)       ✓ include 3 more pkgs from k8s.io/api@2d6f90ab1293a1fb871cf149423ebb72aa7423aa
(9)     ? attempt github.com/go-logr/logr with 1 pkgs; 2 versions to try
(10)      try github.com/go-logr/logr@v0.1.0
(10)  ✓ select github.com/go-logr/logr@v0.1.0 w/1 pkgs
(10)  ? attempt github.com/mattbaird/jsonpatch with 1 pkgs; 1 versions to try
(11)      try github.com/mattbaird/jsonpatch@master
(11)  ✓ select github.com/mattbaird/jsonpatch@master w/1 pkgs
(11)  ? attempt k8s.io/apimachinery with 10 pkgs; 171 versions to try
(12)      try k8s.io/apimachinery@103fd098999dc9c0c88536f5c9ad2e5da39373ae
(12)  ✓ select k8s.io/apimachinery@103fd098999dc9c0c88536f5c9ad2e5da39373ae w/33 pkgs
(12)  ? attempt github.com/google/gofuzz with 1 pkgs; 1 versions to try
(13)      try github.com/google/gofuzz@master
(13)  ✓ select github.com/google/gofuzz@master w/1 pkgs
(13)  ? attempt github.com/go-logr/zapr with 1 pkgs; 2 versions to try
(14)      try github.com/go-logr/zapr@v0.1.0
(14)  ✓ select github.com/go-logr/zapr@v0.1.0 w/1 pkgs
(14)  ? attempt k8s.io/code-generator with 7 pkgs; 147 versions to try
(15)      try k8s.io/code-generator@6702109cc68eb6fe6350b83e14407c8d7309fd1a
(15)  ✓ select k8s.io/code-generator@6702109cc68eb6fe6350b83e14407c8d7309fd1a w/24 pkgs
(15)  ? revisit k8s.io/gengo to add 5 pkgs
(16)    ✓ include 8 more pkgs from k8s.io/gengo@master
(15)  ? attempt github.com/pborman/uuid with 1 pkgs; 8 versions to try
(17)      try github.com/pborman/uuid@v1.2
(17)  ✓ select github.com/pborman/uuid@v1.2 w/1 pkgs
(16)  ? attempt k8s.io/kube-openapi with 1 pkgs; 5 versions to try
(18)      try k8s.io/kube-openapi@master
(18)  ✓ select k8s.io/kube-openapi@master w/5 pkgs
(17)  ? revisit k8s.io/gengo to add 1 pkgs
(19)    ✓ include 1 more pkgs from k8s.io/gengo@master
(17)  ? revisit k8s.io/apimachinery to add 2 pkgs
(20)    ✓ include 21 more pkgs from k8s.io/apimachinery@103fd098999dc9c0c88536f5c9ad2e5da39373ae
(17)  ? revisit k8s.io/apimachinery to add 1 pkgs
(21)    ✓ include 9 more pkgs from k8s.io/apimachinery@103fd098999dc9c0c88536f5c9ad2e5da39373ae
(17)  ? attempt go.uber.org/zap with 2 pkgs; 24 versions to try
(22)      try go.uber.org/zap@v1.9.1
(22)  ✓ select go.uber.org/zap@v1.9.1 w/6 pkgs
(18)  ? attempt github.com/google/uuid with 1 pkgs; 9 versions to try
(23)      try github.com/google/uuid@v1.0.0
(23)  ✓ select github.com/google/uuid@v1.0.0 w/1 pkgs
(19)  ? attempt golang.org/x/net with 1 pkgs; 7 versions to try
(24)      try golang.org/x/net@master
(24)  ✓ select golang.org/x/net@master w/4 pkgs
(20)  ? revisit k8s.io/apimachinery to add 3 pkgs
(25)    ✓ include 3 more pkgs from k8s.io/apimachinery@103fd098999dc9c0c88536f5c9ad2e5da39373ae
(20)  ? attempt github.com/ghodss/yaml with 1 pkgs; 3 versions to try
(26)      try github.com/ghodss/yaml@v1.0.0
(26)  ✓ select github.com/ghodss/yaml@v1.0.0 w/1 pkgs
(21)  ? attempt github.com/golang/glog with 1 pkgs; 1 versions to try
(27)      try github.com/golang/glog@master
(27)  ✓ select github.com/golang/glog@master w/1 pkgs
(22)  ? attempt go.uber.org/multierr with 1 pkgs; 5 versions to try
(28)      try go.uber.org/multierr@v1.1.0
(28)  ✓ select go.uber.org/multierr@v1.1.0 w/1 pkgs
(23)  ? attempt k8s.io/client-go with 12 pkgs; 192 versions to try
(29)      try k8s.io/client-go@1f13a808da65775f22cbf47862c4e5898d8f4ca1
(29)  ✓ select k8s.io/client-go@1f13a808da65775f22cbf47862c4e5898d8f4ca1 w/61 pkgs
(24)  ? revisit k8s.io/api to add 27 pkgs
(30)    ✓ include 28 more pkgs from k8s.io/api@2d6f90ab1293a1fb871cf149423ebb72aa7423aa
(24)  ? attempt github.com/golang/groupcache with 1 pkgs; 1 versions to try
(31)      try github.com/golang/groupcache@master
(31)  ✓ select github.com/golang/groupcache@master w/1 pkgs
(25)  ? revisit k8s.io/apimachinery to add 15 pkgs
(32)    ✓ include 39 more pkgs from k8s.io/apimachinery@103fd098999dc9c0c88536f5c9ad2e5da39373ae
(25)  ? revisit k8s.io/kube-openapi to add 1 pkgs
(33)    ✓ include 1 more pkgs from k8s.io/kube-openapi@master
(25)  ? attempt golang.org/x/time with 1 pkgs; 1 versions to try
(34)      try golang.org/x/time@master
(34)  ✓ select golang.org/x/time@master w/1 pkgs
(26)  ? attempt github.com/golang/protobuf with 1 pkgs; 8 versions to try
(35)      try github.com/golang/protobuf@v1.2.0
(35)  ✓ select github.com/golang/protobuf@v1.2.0 w/1 pkgs
(27)  ? attempt golang.org/x/text with 3 pkgs; 5 versions to try
(36)      try golang.org/x/text@v0.3.0
(36)  ✓ select golang.org/x/text@v0.3.0 w/14 pkgs
(28)  ? attempt github.com/gregjones/httpcache with 2 pkgs; 2 versions to try
(37)      try github.com/gregjones/httpcache@master
(37)  ✓ select github.com/gregjones/httpcache@master w/2 pkgs
(29)  ? attempt gopkg.in/inf.v0 with 1 pkgs; 2 versions to try
(38)      try gopkg.in/inf.v0@v0.9.1
(38)  ✓ select gopkg.in/inf.v0@v0.9.1 w/1 pkgs
(30)  ? attempt github.com/peterbourgon/diskv with 1 pkgs; 4 versions to try
(39)      try github.com/peterbourgon/diskv@v2.0.1
(39)  ✓ select github.com/peterbourgon/diskv@v2.0.1 w/1 pkgs
(31)  ? revisit k8s.io/client-go to add 1 pkgs
(40)    ✓ include 17 more pkgs from k8s.io/client-go@1f13a808da65775f22cbf47862c4e5898d8f4ca1
(31)  ? revisit k8s.io/apimachinery to add 1 pkgs
(41)    ✓ include 1 more pkgs from k8s.io/apimachinery@103fd098999dc9c0c88536f5c9ad2e5da39373ae
(31)  ? attempt github.com/google/btree with 1 pkgs; 1 versions to try
(42)      try github.com/google/btree@master
(42)  ✓ select github.com/google/btree@master w/1 pkgs
(32)  ? attempt golang.org/x/oauth2 with 2 pkgs; 1 versions to try
(43)      try golang.org/x/oauth2@master
(43)  ✓ select golang.org/x/oauth2@master w/5 pkgs
(33)  ? revisit golang.org/x/net to add 1 pkgs
(44)    ✓ include 1 more pkgs from golang.org/x/net@master
(33)  ? attempt github.com/petar/GoLLRB with 1 pkgs; 2 versions to try
(45)      try github.com/petar/GoLLRB@master
(45)  ✓ select github.com/petar/GoLLRB@master w/1 pkgs
(34)  ? attempt github.com/imdario/mergo with 1 pkgs; 20 versions to try
(46)      try github.com/imdario/mergo@v0.3.6
(46)  ✓ select github.com/imdario/mergo@v0.3.6 w/1 pkgs
(35)  ? attempt github.com/googleapis/gnostic with 1 pkgs; 14 versions to try
(47)      try github.com/googleapis/gnostic@v0.2.0
(47)  ✓ select github.com/googleapis/gnostic@v0.2.0 w/3 pkgs
(36)  ? revisit github.com/golang/protobuf to add 2 pkgs
(48)    ✓ include 5 more pkgs from github.com/golang/protobuf@v1.2.0
(36)  ? attempt github.com/go-openapi/spec with 1 pkgs; 10 versions to try
(49)      try github.com/go-openapi/spec@v0.17.2
(49)  ✓ select github.com/go-openapi/spec@v0.17.2 w/1 pkgs
(37)  ? attempt go.uber.org/atomic with 1 pkgs; 9 versions to try
(50)      try go.uber.org/atomic@v1.3.2
(50)  ✓ select go.uber.org/atomic@v1.3.2 w/1 pkgs
(38)  ? attempt github.com/emicklei/go-restful with 1 pkgs; 25 versions to try
(51)      try github.com/emicklei/go-restful@v2.8.0
(51)  ✓ select github.com/emicklei/go-restful@v2.8.0 w/2 pkgs
(39)  ? attempt golang.org/x/crypto with 1 pkgs; 2 versions to try
(52)      try golang.org/x/crypto@master
(52)  ✓ select golang.org/x/crypto@master w/1 pkgs
(40)  ? attempt golang.org/x/sys with 2 pkgs; 2 versions to try
(53)      try golang.org/x/sys@master
(53)  ✓ select golang.org/x/sys@master w/2 pkgs
(41)  ? attempt github.com/json-iterator/go with 1 pkgs; 25 versions to try
(54)      try github.com/json-iterator/go@v1.1.5
(54)  ✓ select github.com/json-iterator/go@v1.1.5 w/1 pkgs
(42)  ? attempt github.com/go-openapi/swag with 1 pkgs; 7 versions to try
(55)      try github.com/go-openapi/swag@v0.17.2
(55)  ✓ select github.com/go-openapi/swag@v0.17.2 w/1 pkgs
(43)  ? attempt github.com/mailru/easyjson with 2 pkgs; 2 versions to try
(56)      try github.com/mailru/easyjson@master
(56)  ✓ select github.com/mailru/easyjson@master w/3 pkgs
(44)  ? attempt github.com/davecgh/go-spew with 1 pkgs; 4 versions to try
(57)      try github.com/davecgh/go-spew@v1.1.1
(57)  ✓ select github.com/davecgh/go-spew@v1.1.1 w/1 pkgs
(45)  ? attempt github.com/modern-go/reflect2 with 1 pkgs; 4 versions to try
(58)      try github.com/modern-go/reflect2@1.0.1
(58)  ✓ select github.com/modern-go/reflect2@1.0.1 w/1 pkgs
(46)  ? attempt github.com/modern-go/concurrent with 1 pkgs; 5 versions to try
(59)      try github.com/modern-go/concurrent@1.0.3
(59)  ✓ select github.com/modern-go/concurrent@1.0.3 w/1 pkgs
(47)  ? attempt github.com/hashicorp/golang-lru with 1 pkgs; 3 versions to try
(60)      try github.com/hashicorp/golang-lru@v0.5.0
(60)  ✓ select github.com/hashicorp/golang-lru@v0.5.0 w/2 pkgs
(48)  ? attempt cloud.google.com/go with 1 pkgs; 38 versions to try
(61)      try cloud.google.com/go@v0.33.0
(61)  ✓ select cloud.google.com/go@v0.33.0 w/1 pkgs
(49)  ? attempt google.golang.org/appengine with 2 pkgs; 12 versions to try
(62)      try google.golang.org/appengine@v1.3.0
(62)  ✓ select google.golang.org/appengine@v1.3.0 w/10 pkgs
(50)  ? revisit golang.org/x/net to add 1 pkgs
(63)    ✓ include 1 more pkgs from golang.org/x/net@master
(50)  ? attempt gopkg.in/yaml.v2 with 1 pkgs; 6 versions to try
(64)      try gopkg.in/yaml.v2@v2.2.1
(64)  ✓ select gopkg.in/yaml.v2@v2.2.1 w/1 pkgs
(51)  ? attempt github.com/go-openapi/jsonreference with 1 pkgs; 6 versions to try
(65)      try github.com/go-openapi/jsonreference@v0.17.2
(65)  ✓ select github.com/go-openapi/jsonreference@v0.17.2 w/1 pkgs
(52)  ? attempt github.com/go-openapi/jsonpointer with 1 pkgs; 6 versions to try
(66)      try github.com/go-openapi/jsonpointer@v0.17.2
(66)  ✓ select github.com/go-openapi/jsonpointer@v0.17.2 w/1 pkgs
(53)  ? attempt github.com/PuerkitoBio/purell with 1 pkgs; 8 versions to try
(67)      try github.com/PuerkitoBio/purell@v1.1.0
(67)  ✓ select github.com/PuerkitoBio/purell@v1.1.0 w/1 pkgs
(54)  ? revisit golang.org/x/text to add 1 pkgs
(68)    ✓ include 6 more pkgs from golang.org/x/text@v0.3.0
(54)  ? attempt github.com/PuerkitoBio/urlesc with 1 pkgs; 1 versions to try
(69)      try github.com/PuerkitoBio/urlesc@master
(69)  ✓ select github.com/PuerkitoBio/urlesc@master w/1 pkgs
(55)  ? revisit golang.org/x/net to add 1 pkgs
(70)    ✓ include 1 more pkgs from golang.org/x/net@master
  ✓ found solution with 291 packages from 54 projects

Solver wall times by segment:
     b-list-versions: 49.817609862s
         b-list-pkgs: 13.368487525s
              b-gmal: 10.934344584s
     b-source-exists:  8.464330823s
  b-deduce-proj-root:  2.378990602s
    b-rev-present-in:   83.870506ms
             satisfy:   82.865313ms
         select-atom:   70.197054ms
         select-root:    5.928492ms
            new-atom:    3.542508ms
               other:     590.933µs
            add-atom:     130.026µs
          b-pair-rev:       75.48µs
           b-matches:      25.577µs
      b-pair-version:      17.054µs

  TOTAL: 1m25.211006339s

(1/54) Wrote github.com/PuerkitoBio/urlesc@master
(2/54) Wrote github.com/golang/glog@master
(3/54) Wrote github.com/PuerkitoBio/purell@v1.1.0
(4/54) Wrote github.com/go-logr/zapr@v0.1.0
(5/54) Wrote github.com/go-openapi/jsonreference@v0.17.2
(6/54) Wrote github.com/ghodss/yaml@v1.0.0
(7/54) Wrote github.com/google/btree@master
(8/54) Wrote github.com/golang/groupcache@master
(9/54) Wrote github.com/google/gofuzz@master
(10/54) Wrote github.com/google/uuid@v1.0.0
(11/54) Wrote github.com/go-openapi/jsonpointer@v0.17.2
(12/54) Wrote github.com/go-logr/logr@v0.1.0
(13/54) Wrote github.com/go-openapi/swag@v0.17.2
(14/54) Wrote github.com/davecgh/go-spew@v1.1.1
(15/54) Wrote github.com/gregjones/httpcache@master
(16/54) Wrote github.com/spf13/pflag@v1.0.3
(17/54) Wrote github.com/emicklei/go-restful@v2.8.0
(18/54) Wrote github.com/imdario/mergo@v0.3.6
(19/54) Wrote github.com/mattbaird/jsonpatch@master
(20/54) Wrote github.com/modern-go/reflect2@1.0.1
(21/54) Wrote github.com/modern-go/concurrent@1.0.3
(22/54) Wrote github.com/mailru/easyjson@master
(23/54) Wrote github.com/pborman/uuid@v1.2
(24/54) Wrote github.com/hashicorp/golang-lru@v0.5.0
(25/54) Wrote github.com/peterbourgon/diskv@v2.0.1
(26/54) Wrote go.uber.org/multierr@v1.1.0
(27/54) Wrote go.uber.org/atomic@v1.3.2
(28/54) Wrote gopkg.in/inf.v0@v0.9.1
(29/54) Wrote gopkg.in/yaml.v2@v2.2.1
(30/54) Wrote github.com/json-iterator/go@v1.1.5
(31/54) Wrote google.golang.org/appengine@v1.3.0
(32/54) Wrote github.com/go-openapi/spec@v0.17.2
(33/54) Wrote github.com/golang/protobuf@v1.2.0
(34/54) Wrote k8s.io/klog@v0.1.0
(35/54) Wrote golang.org/x/time@master
(36/54) Wrote go.uber.org/zap@v1.9.1
(37/54) Wrote k8s.io/kube-openapi@master
(38/54) Wrote k8s.io/gengo@master
(39/54) Wrote github.com/petar/GoLLRB@master
(40/54) Wrote github.com/operator-framework/operator-sdk@master
(41/54) Wrote golang.org/x/oauth2@master
(42/54) Wrote github.com/googleapis/gnostic@v0.2.0
(43/54) Wrote k8s.io/apimachinery@103fd098999dc9c0c88536f5c9ad2e5da39373ae
(44/54) Wrote k8s.io/api@2d6f90ab1293a1fb871cf149423ebb72aa7423aa
(45/54) Wrote golang.org/x/crypto@master
(46/54) Wrote golang.org/x/sys@master
(47/54) Wrote k8s.io/code-generator@6702109cc68eb6fe6350b83e14407c8d7309fd1a
(48/54) Wrote golang.org/x/net@master
(49/54) Wrote github.com/gogo/protobuf@v1.1.1
(50/54) Wrote k8s.io/client-go@1f13a808da65775f22cbf47862c4e5898d8f4ca1
(51/54) Wrote golang.org/x/text@v0.3.0
(52/54) Wrote cloud.google.com/go@v0.33.0
(53/54) Wrote golang.org/x/tools@master
(54/54) Wrote sigs.k8s.io/controller-runtime@v0.1.7
Run dep ensure done
Run git init ...
Initialized empty Git repository in /Users/mhausenblas/Dropbox/dev/work/src/github.com/mhausenblas/nodefpol-operator/app-operator/.git/
Auto packing the repository in background for optimum performance.
See "git help gc" for manual housekeeping.
Run git init done
```