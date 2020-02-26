# Kubernetes 三层网络方案

## host-gw 模式

> 工作原理: 将每个 Flannel 子网的“下一跳”，设置成了该子网对应的宿主机的 IP 地址
> 工作的核心: 就在于 IP 包在封装成帧发送出去的时候，会使用路由表里的“下一跳”来设置目的 MAC 地址
> Flannel host-gw 模式必须要求集群宿主机之间是二层连通的

## Calico

> Calico 项目提供的网络解决方案，与 Flannel 的 host-gw 模式，几乎是完全一样的
> 不同点： 不同于 Flannel 通过 Etcd 和宿主机上的 flanneld 来维护路由信息的做法，Calico 项目使用了一个“重型武器”来自动地在整个集群中分发路由信息
> (BGP 的全称是 Border Gateway Protocol，即：边界网关协议)

Calico 三个部分组成

1. Calico 的 CNI 插件。这是 Calico 与 Kubernetes 对接的部分
2. Felix。它是一个 DaemonSet，负责在宿主机上插入路由规则
3. BIRD。它就是 BGP 的客户端，专门负责在集群里分发路由规则信息
