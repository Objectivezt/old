# Operator

> 一个相对更加灵活和编程友好的管理“有状态应用”的解决方案

## Etcd Operator 的使用方法

> Etcd Operator 部署 Etcd 集群，采用的是静态集群（Static）的方式。

1. `git clone https://github.com/coreos/etcd-operator`
2. `example/rbac/create_role.sh` Etcd Operator 部署在 Kubernetes 集群里

### create_role.sh 作用

1. 对 Pod、Service、PVC、Deployment、Secret 等 API 对象，有所有权限；
2. 对 CRD 对象，有所有权限；
3. 对属于 etcd.database.coreos.com 这个 API Group 的 CR（Custom Resource）对象，有所有权限。

Operator 的工作原理，实际上是利用了 Kubernetes 的自定义 API 资源（CRD），来描述我们想要部署的“有状态应用”；然后在自定义控制器里，根据自定义 API 对象的变化，来完成具体的部署和运维工作。

### addOneMember

1. 生成一个新节点的 Pod 的名字，比如：example-etcd-cluster-v6v6s6stxd；
2. 调用 Etcd Client，执行前面提到过的 etcdctl member add example-etcd-cluster-v6v6s6stxd 命令；
3. 使用这个 Pod 名字，和已经存在的所有节点列表，组合成一个新的 initial-cluster 字段的值；
4. 使用这个 initial-cluster 的值，生成这个 Pod 里 Etcd 容器的启动命令。
