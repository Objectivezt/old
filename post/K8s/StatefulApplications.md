# Stateful applications

## 部署的“有状态应用”

> 部署一个 MySql 集群

1. 是一个“主从复制”（Maser-Slave Replication）的 MySQL 集群；
2. 有 1 个主节点（Master）；
3. 有多个从节点（Slave）；
4. 从节点需要能水平扩展；
5. 所有的写操作，只能在主节点上执行；
6. 读操作可以在所有节点上执行;

### 通过 XtraBackup 将 Master 节点的数据备份到指定目录

> XtraBackup 是业界主要使用的开源 MySQL 备份和恢复工具

### 配置 Slave 节点

> Slave 节点在第一次启动前，需要先把 Master 节点的备份数据，连同备份信息文件，一起拷贝到自己的数据目录（/var/lib/mysql）下

### 启动 Slave 节点

```
TheSlave|mysql> START SLAVE;
```

### 在这个集群中添加更多的 Slave 节点

## 解决问题

> 将部署 MySQL 集群的流程迁移到 Kubernetes 项目上，需要能够“容器化”地解决下面的“三座大山”：

1. Master 节点和 Slave 节点需要有不同的配置文件（即：不同的 my.cnf）；
2. Master 节点和 Slave 节点需要能够传输备份信息文件；
3. 在 Slave 节点第一次启动之前，需要执行一些初始化 SQL 操作；
