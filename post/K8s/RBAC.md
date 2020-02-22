# RBAC

> 在 Kubernetes 项目中，负责完成授权（Authorization）工作的机制，就是 RBAC, 基于角色的访问控制（Role-Based Access Control）。

## 三个最基本的概念

- Role：角色，它其实是一组规则，定义了一组对 Kubernetes API 对象的操作权限。
- Subject：被作用者，既可以是“人”，也可以是“机器”，也可以使你在 Kubernetes 里定义的“用户”。
- RoleBinding：定义了“被作用者”和“角色”的绑定关系。而这三个概念，其实就是整个 RBAC 体系的核心所在。

## Role

> Role 对象指定了它能产生作用的 Namepace 是：mynamespace。

### 为 ServiceAccount 分配权限的过程

1. 我们要定义一个 ServiceAccount。
2. 通过编写 RoleBinding 的 YAML 文件，来为这个 ServiceAccount 分配权限
3. 用 kubectl 命令创建这三个对象

## ClusterRole

> Kubernetes 还提供了四个预先定义好的 ClusterRole 来供用户直接使用：cluster-admin；admin；edit；view。
