# 备份恢复-同可用区

同可用区版本TiDB实例备份恢复依赖UFile Bucket，需创建私有空间并获取公司钥。同可用区版本TiDB暂时只支持定时备份。

## 创建私有空间并获取令牌

进入UFile控制台：https://console.ucloud.cn/ufile/ufile 创建一个北京的私有空间。

选择有效时常（和备份空间生效有关，建议一年），选择刚刚新建的私有空间，勾选 上传 下载 删除 文件列表 4个权限。
![](http://tidb-docs.cn-bj.ufileos.com/backupnew001.png)

记录公私钥
![](http://tidb-docs.cn-bj.ufileos.com/backupnew002.png)



## 设置备份策略



| 参数| 说明 | 
| ------ | -------- | 
| 是否开启自动备份    |   开启自动备份开关  | 
|备份时间 |每日自动备份时间|
|自动备份保留份数|自动备份会有份数限制，当超过份数上限会删除最早时间的自动备份，最多7份|
|自动备份周期|每隔多少天，执行一次自动备份，最多相隔7天|
|存储空间域名|用于存放TiDB备份文件的UFile存储空间|
|公钥|授权的存储空间公钥|
|私钥|授权的存储空间私钥|

![](http://tidb-docs.cn-bj.ufileos.com/backupnew004.png)


## 备份恢复

TiDB当前支持从备份文件恢复至一个新的TiDB实例，且无法跨类型恢复。需要用户提前准备好新实例，恢复工作会覆盖新实例数据，选择时请注意。

![](http://tidb-docs.cn-bj.ufileos.com/backup004.png)

选择后可以在恢复菜单查看是否完成。

