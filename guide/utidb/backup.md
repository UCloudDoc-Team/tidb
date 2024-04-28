

# 备份恢复

TiDB服务会备份数据到用户的US3-Bucket，方便用户自助下载。 需要用户账号开通US3权限，并授权操作（创建bucket，上传备份文件，下载备份文件用于恢复）US3产品。

![](https://tidb-doc.cn-bj.ufileos.com/utidb/backup_auth.png)
![](https://tidb-doc.cn-bj.ufileos.com/utidb/utidb-listbackup.png)
![](https://tidb-doc.cn-bj.ufileos.com/utidb/utidb-listrestore.png)

## 设置备份策略

| 参数| 说明 | 
| ------ | -------- | 
| 是否开启自动备份    |   开启自动备份开关  | 
|备份时间 |每日自动备份时间|
|自动备份保留份数|自动备份会有份数限制，当超过份数上限会删除最早时间的自动备份，最多7份|
|自动备份周期|每隔多少天，执行一次自动备份，最多相隔7天|

![](https://tidb-doc.cn-bj.ufileos.com/utidb/utidb-autobackup01.png)

## 调整自动备份策略

可以在备份菜单中调整是否要开启自动备份，以及备份的策略

![](https://tidb-doc.cn-bj.ufileos.com/utidb/utidb-autobackup02.png)


## 手动备份

除了自动备份，TiDB还提供手动备份选择，手动备份最多同时保留7份。

![](https://tidb-doc.cn-bj.ufileos.com/utidb/utidb-startbackup.png)


## 删除备份数据

备份数据支持手动删除，用户可以手动删除历史备份数据(包括自动和手动备份数据)。

在备份列表操作中，选择‘删除’按钮，删除备份数据

![](https://tidb-doc.cn-bj.ufileos.com/utidb/utidb_deletebackup.png)

## 备份恢复

TiDB当前支持从备份文件恢复至一个新的TiDB实例。需要用户提前准备好新实例，恢复工作会覆盖新实例数据，选择时请注意。

在备份列表操作中，选择‘恢复’按钮，开始恢复任务

![](https://tidb-doc.cn-bj.ufileos.com/utidb/utidb-startrestore.png)

选择后可以在恢复菜单查看是否完成。

