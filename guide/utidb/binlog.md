

# Binlog 同步

Binlog 同步功能可将 TiDB 的增量数据实时同步到其他存储中。 支持 MySQL、TiDB、Kafka、US3作为目标存储。

## 进入管理页面

在产品主页中找到对应的实例， 点击“详情”按钮进入详情页面。

![](https://tidb-doc.cn-bj.ufileos.com/utidb/tidb-list.png)

## 开启 Binlog

切换到 “Binlog” 面板

![](https://tidb-doc.cn-bj.ufileos.com/utidb/binlog_start.png)

Binlog 同步服务默认不开启，点击开启Binlog按钮打开开启窗口

![](https://tidb-doc.cn-bj.ufileos.com/utidb/binlog_starting.png)

选择合适节点配置和节点数量后，确认费用无误后，点击立即购买

成功开启后状态更新为“已开启”
![](https://tidb-doc.cn-bj.ufileos.com/utidb/binlog_started.png)

## 全量数据迁移，记录CommitTS数据

推荐使用[UDTS](https://docs.ucloud.cn/udts/type/tidb)进行全量迁移，成功完成全量迁移后，UDTS会返回CommitTS数据。 

![](https://tidb-doc.cn-bj.ufileos.com/utidb/binlog_stats.png)

> 如果当前为空数据库或者不需要迁移存量数据的时候可不进行全量迁移，通过下图方式获取当前CommitTS。
![](https://tidb-doc.cn-bj.ufileos.com/utidb/binlog_commitTs.png)

## 添加消费者

点击“添加消费者”按钮打开添加窗口， 可为一个实例添加多个消费者。
![](https://tidb-doc.cn-bj.ufileos.com/utidb/binlog_consumer.png)

选择MySQL协议消费者（如MySQL数据库、TiDB数据库或者其它兼容MySQL协议的数据库）或者Kafka， 输入上一步中获取的CommitTS数据以及其它需求信息完成添加。
![](https://tidb-doc.cn-bj.ufileos.com/utidb/binlog_add_consumer.png)

## 查看消费者

当前已有的消费者会自动列出

![](https://tidb-doc.cn-bj.ufileos.com/utidb/binlog_consumer_list.png)

## 删除消费者

当需要删除某个消费者的时候， 可通过“删除”按钮删除。

![](https://tidb-doc.cn-bj.ufileos.com/utidb/binlog_delete_consumer.png)

## 关闭 Binlog

在不需要使用Binlog功能时建议关闭Binlog服务。即可降低成本，又可提高性能。

>在关闭Binlog之前必需先删除所有的消费者。

点击图示按钮关闭Binlog服务。
![](https://tidb-doc.cn-bj.ufileos.com/utidb/binlog_stopping.png)
