{{indexmenu_n>17}}

# Binlog同步

Binlog同步功能可将TiDB的增量数据实时同步到其他存储中。当前支持MySQL，TiDB作为目标存储

## 步骤一 开启Binlog

确保Binlog状态为“已开启”

![](http://tidb-docs.cn-bj.ufileos.com/binlogopen001.png)

## 步骤二 获取Binlog状态，记录CommitTS数据，使用工具或者UDTS进行全量迁移

如果当前为空数据库可不用全量迁移。

![](http://tidb-docs.cn-bj.ufileos.com/committs001.png)

## 步骤三 使用步骤二中的CommitTS数据，添加消费者

![](http://tidb-docs.cn-bj.ufileos.com/addconsumer001.png)
