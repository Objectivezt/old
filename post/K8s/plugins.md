# k8s plugins

## FlexVolume

> 指定了这个 Volume 的 driver 叫作 k8s/nfs
> 当编写完了 FlexVolume 的实现之后，一定要把它的可执行文件放在每个节点的插件目录下
> FlexVolume 每一次对插件可执行文件的调用，都是一次完全独立的操作

mount 参数后面的两个字段：`<mount dir>`和 `<json params>`

1. `<json params>`，是一个 JSON Map 格式的参数列表。我们在前面 PV 里定义的 options 字段的值，都会被追加在这个参数里
2. `<mount dir>`，是 kubelet 调用 SetUpAt() 方法传递来的 dir 的值

### driver

> driver 字段的格式是：vendor/driver

## CSI

> CSI 插件体系的设计思想，就是把这个 Provision 阶段，以及 Kubernetes 里的一部分存储管理功能，从主干代码里剥离出来，做成了几个单独的组件

1. Driver Registrar 组件，负责将插件注册到 kubelet 里面
2. External Provisioner 组件，负责的正是 Provision 阶段
3. External Attacher 组件，负责的正是“Attach 阶段”
