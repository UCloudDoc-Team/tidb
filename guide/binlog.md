

# Binlog 同步

Binlog 同步功能可将 TiDB 的增量数据实时同步到其他存储中。 支持 MySQL、TiDB、Kafka 作为目标存储。

## 步骤一 开启Binlog

确保Binlog状态为“已开启”

![](http://tidb-docs.cn-bj.ufileos.com/binlogopen001.png)

## 步骤二 全量数据迁移，记录CommitTS数据

推荐使用[UDTS](https://docs.ucloud.cn/udts/type/tidb)进行全量迁移，成功完成全量迁移后，会返回CommitTS数据。 

> 如果当前为空数据库可不进行全量迁移，通过下图方式获取CommitTS。
![](http://tidb-docs.cn-bj.ufileos.com/committs001.png)

## 步骤三 使用步骤二中的CommitTS数据，添加消费者

![](http://tidb-docs.cn-bj.ufileos.com/addconsumer.png)
