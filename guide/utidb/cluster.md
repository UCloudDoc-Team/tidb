
# 集群管理

集群管理提供用户对集群进行各项运维操作功能

## 操作入口

在产品主页中找到对应的实例， 在操作列中点击"集群管理",选择对应要进行的运维操作。

![](https://tidb-doc.cn-bj.ufileos.com/utidb/utidb-cluster-manager.png)

## 扩容节点

扩容节点支持用户扩容集群节点数量，单次操作仅支持操作一类角色节点

Binlog和TiFlash角色在开启对应服务后才能展示选择

集群管理中选择‘扩容节点’，打开扩容窗口
![](https://tidb-doc.cn-bj.ufileos.com/utidb/scaleout_list.png)
选择扩容节点角色、扩容节点数量，确认费用后，点击立即购买
![](https://tidb-doc.cn-bj.ufileos.com/utidb/scaleout.png)

## 缩容节点

缩容节点支持用户缩容集群节点数量，单次操作仅支持操作单角色节点。

只有当集群节点数量支持缩容时，该功能才会开放。

集群管理中选择‘缩容节点’, 打开缩容窗口
![](https://tidb-doc.cn-bj.ufileos.com/utidb/scalein_list.png)

选择缩容节点角色后，会列出当前支持缩容节点列表（当前角色节点数量不支持缩容时，禁用该角色选项）
选择要缩容节点，确认退费金额后，点击立即购买
![](https://tidb-doc.cn-bj.ufileos.com/utidb/scalein.png)

## 配置升降级

配置升降级支持用户对集群节点进行规格的修改，单次操作仅支持操作一类角色节点

集群管理中选择‘配置升降级’，打开配置窗口
![](https://tidb-doc.cn-bj.ufileos.com/utidb/adjust-uhost001.png)

选择要修改的角色，修改对应的节点规格，确认费用后，点击立即购买
![](https://tidb-doc.cn-bj.ufileos.com/utidb/scale_config2.png)

## 磁盘扩缩容

磁盘扩缩容支持用户扩缩节点磁盘容量，单次操作仅支持操作单角色节点。

集群管理中选择‘磁盘扩缩容’, 打开磁盘扩缩容窗口
![](https://tidb-doc.cn-bj.ufileos.com/utidb/adjust-disk001.png)

选择待操作节点角色后，调整对应角色节点磁盘容量，确认变更金额后，点击立即购买
> 注意：缩容磁盘容量时，会滚动重启节点，过程中集群性能会有影响，请谨慎操作
![](https://tidb-doc.cn-bj.ufileos.com/utidb/scalein.png)
