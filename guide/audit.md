

# 数据库审计

数据库审计使用云数据库审计系统（Udss）资源，用户使用前需先创建Udss实例

## 开启数据库审计

可以在概览审计信息中开启数据库审计，如未创建Udss，可跳转至Udss创建实例

开启审计后会部署Udss审计agent服务，具体审计使用请参考Udss文档：https://docs.ucloud.cn/udas/README

![](https://tidb-doc.cn-bj.ufileos.com/audit/start-audit.png)


## 关闭数据库审计

可以在概览审计信息中关闭数据库审计

关闭后会删除Udss审计agent服务，Udss停止/删除请至Udss控制台操作

![](https://tidb-doc.cn-bj.ufileos.com/audit/stop-audit.png)

## 审计详情

可在实例详情概览查看审计信息详情

审计信息展示，UTiDB审计状态，Udss实例名称，Udss审计实例内网Ip

![](https://tidb-doc.cn-bj.ufileos.com/audit/audit-info.png)
