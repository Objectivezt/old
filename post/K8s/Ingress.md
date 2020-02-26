# Ingress

> Ingress，就是 Service 的“Service”, 为了代理不同后端 Service 而设置的负载均衡
> Ingress 对象，其实就是 Kubernetes 项目对“反向代理”的一种抽象
> Ingress 只能工作在七层，而 Service 只能工作在四层。如果需要 在 Kubernetes 里为应用进行 TLS 配置等 HTTP 相关的操作时，都必须通过 Ingress 来进行
> 生产环境中，Ingress 带来的灵活度和自由度

## IngressRule

> IngressRule 的 Key，就叫做：host。它必须是一个标准的域名格式（Fully Qualified Domain Name）的字符串，而不能是 IP 地址
> IngressRule 规则的定义，则依赖于 path 字段。这里的每一个 path 都对应一个后端 Service。

## 安装步骤

1. 在集群里部署我们的应用 Pod 和它们对应的 Service
2. 创建 Ingress 所需的 SSL 证书（tls.crt）和密钥（tls.key）
3. 定义的 Ingress 对象
4. 通过访问这个 Ingress 的地址和端口，访问到我们前面部署的应用
