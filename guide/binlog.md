

# Binlog 同步

Binlog 同步功能可将 TiDB 的增量数据实时同步到其他存储中。 支持 MySQL、TiDB、Kafka 作为目标存储。

## 进入管理页面

在产品主页中找到对应的实例， 点击“详情”按钮进入详情页面。

![](http://tidb-doc.cn-bj.ufileos.com/basic/instance.list.detail.button.png)

## 开启 Binlog

切换到 “Binlog同步” 面板

![](http://tidb-doc.cn-bj.ufileos.com/binlog/binlog1.png)

Binlog 同步服务默认不开启，点击图示开关打开开启窗口 

![](http://tidb-doc.cn-bj.ufileos.com/binlog/binlog.enable.png)

设置Binlog保存周期， 默认为“7”， 保存7天（支持范围1～14天）。
![](http://tidb-doc.cn-bj.ufileos.com/binlog/binlog.enalbe.gc.png)

成功开启后状态更新为“已开启”
![](http://tidb-doc.cn-bj.ufileos.com/binlog/binlog.enabled.png)

## 全量数据迁移，记录CommitTS数据

推荐使用[UDTS](https://docs.ucloud.cn/udts/type/tidb)进行全量迁移，成功完成全量迁移后，UDTS会返回CommitTS数据。 

![](http://tidb-doc.cn-bj.ufileos.com/binlog/binlog.fullAndInc.png)

> 如果当前为空数据库或者不需要迁移存量数据的时候可不进行全量迁移，通过下图方式获取当前CommitTS。
![](http://tidb-docs.cn-bj.ufileos.com/committs001.png)

## 添加消费者

## 查看消费者

## 删除消费者

## 修改 Binlog GC

## 关闭 Binlog


## 步骤一 开启Binlog

确保Binlog状态为“已开启”

![](http://tidb-docs.cn-bj.ufileos.com/binlogopen001.png)

## 步骤二 全量数据迁移，记录CommitTS数据



## 步骤三 使用步骤二中的CommitTS数据，添加消费者

![](http://tidb-docs.cn-bj.ufileos.com/addconsumer.png)
