# Network Namespace

## 网络栈

> 作为一个容器，它可以声明直接使用宿主机的网络栈（–net=host），即：不开启 Network Namespace

1. 网卡（Network Interface）
2. 回环设备（Loopback Device）、
3. 路由表（Routing Table）
4. iptables 规则

在大多数情况下，我们都希望容器进程能使用自己 Network Namespace 里的网络栈，即：拥有属于自己的 IP 地址和端口

限制在 Network Namespace 里的容器进程，实际上是通过 Veth Pair 设备 + 宿主机网桥的方式，实现了跟同其他容器的数据交换。

### Overlay Network（覆盖网络）

> 我们需要在已有的宿主机网络上，再通过软件构建一个覆盖在已有宿主机网络之上的、可以把所有容器连通在一起的虚拟网络。

### nginx 内的 ifconfig 可以在容器内安装。

```bash
# apt-get update
# apt install net-tools
```

### Flannel

> lannel 项目本身只是一个框架，真正为我们提供容器网络功能的，是 Flannel 的后端实现。目前，Flannel 支持三种后端实现，分别是：
>
> 1. VXLAN；
> 2. host-gw；
> 3. UDP。
