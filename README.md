
`kubectl create -f mcsh-operator/deploy/crds`

```
root@vps207526:~/mcsh-op/mcsh-operator/deploy/crds# kubectl get crd | grep mcserverhosting.net
bungeeservers.deployments.mcserverhosting.net      2020-03-30T11:51:41Z
minecraftservers.deployments.mcserverhosting.net   2020-03-30T11:51:12Z
restrictions.deployments.mcserverhosting.net       2020-03-30T11:51:12Z
sftpservers.deployments.mcserverhosting.net        2020-03-30T11:51:12Z
```

Ensure you [create a pull secret based on existing docker credentials](https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/#registry-secret-existing-credentials) as [github requires login for pulls](https://github.community/t5/How-to-use-Git-and-GitHub/Error-response-from-daemon-unauthorized-when-I-m-trying-to-pull/m-p/37129/highlight/true#M9382).

`kubectl create -f mcsh-operator/deploy`

```
{"level":"info","ts":1585569489.7739913,"logger":"controller-runtime.controller","msg":"Starting Controller","controller":"restriction-controller"}
{"level":"info","ts":1585569489.7740645,"logger":"controller-runtime.controller","msg":"Starting workers","controller":"restriction-controller","worker count":1}
{"level":"info","ts":1585569489.7745423,"logger":"controller-runtime.controller","msg":"Starting Controller","controller":"minecraftserver-controller"}
{"level":"info","ts":1585569489.7745798,"logger":"controller-runtime.controller","msg":"Starting workers","controller":"minecraftserver-controller","worker count":1}
{"level":"info","ts":1585569489.7751055,"logger":"controller-runtime.controller","msg":"Starting Controller","controller":"sftpserver-controller"}
{"level":"info","ts":1585569489.775135,"logger":"controller-runtime.controller","msg":"Starting workers","controller":"sftpserver-controller","worker count":1}
{"level":"info","ts":1585569489.7751753,"logger":"controller-runtime.controller","msg":"Starting Controller","controller":"bungeeserver-controller"}
{"level":"info","ts":1585569489.775251,"logger":"controller-runtime.controller","msg":"Starting workers","controller":"bungeeserver-controller","worker count":1}
```