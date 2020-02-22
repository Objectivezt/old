# PV、PVC、StorageClass

## PV

> 是持久化存储数据卷

### PV 对象转化为持久化存储

1. Attach，为虚拟机挂载远程磁盘的操作，对应的正是“两阶段处理”的第一阶段。在 Kubernetes 中。
2. Mount， 将磁盘设备格式化并挂载到 Volume 宿主机目录的操作，对应的正是“两阶段处理”的第二个阶段，。

#### 区分 Attach 和 Mount 两个阶段

“第一阶段”（Attach），k8s 提供的可用参数是 nodeName，即宿主机的名字。
“第二阶段”（Mount），k8s 提供的可用参数是 dir，即 Volume 的宿主机目录。

## PVC

> PVC 描述的 Pod 所希望使用的持久化存储的属性

### PVC 和 PV 的绑定

> PVC 和 PV 的设计，和“面向对象”的思想完全一致。

绑定要检查的条件，包括两部分：

1. PV 和 PVC 的 spec 字段。eg，PV 的存储（storage）大小，就必须满足 PVC 的要求。
2. PV 和 PVC 的 storageClassName 字段必须一样。

## StorageClass

1. PV 的属性。比如，存储类型、Volume 的大小等等。
2. 创建这种 PV 需要用到的存储插件。比如，Ceph 等等。
