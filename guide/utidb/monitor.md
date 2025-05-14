

# 监控信息 

按规格售卖TiDB控制台提供监控信息，包含TiDB集群及节点的各项指标，用户可以通过控制台查看当前集群的运行状态

集群监控按监控指标分为集群性能监控和集群节点监控，集群性能监控在详情概览页中展示，集群节点监控在详情的'监控信息'中展示

## 集群性能监控

集群性能监控在详情概览页右下方展示，展示内容包括集群SQL执行时间、QPS、TPS、连接数及连接数使用率等信息

![](https://tidb-doc.cn-bj.ufileos.com/utidb/monitor.png)

## 集群节点监控

集群节点监控在详情页的'监控信息'中展示，展示内容包括集群各节点的CPU、内存、磁盘IO、网络IO等信息
![](https://tidb-doc.cn-bj.ufileos.com/utidb/monitor-node.png)

## 告警配置

进入 资源监控UMon - 告警管理：https://console.ucloud.cn/umonitor/alarmManagement

打开告警策略 - 新建告警策略
![](https://tidb-doc.cn-bj.ufileos.com/monitor/cloudwatch001.png)

1. 资源类型选择 分布式NewSQL数据库TiDB
2. 添加要绑定资源
3. 选择默认告警条件模版或手动配置告警条件
4. 配置通知信息
5. 设置告警策略名称后点击 提交 按钮即可完成告警策略绑定
![](https://tidb-doc.cn-bj.ufileos.com/monitor/createalert002.png)

## 绑定资源

进入 资源监控UMon - 告警管理 - 告警策略：https://console.ucloud.cn/umonitor/alarmManagement/alarmPolicy

选择 要修改告警策略，点击编辑按钮
![](https://tidb-doc.cn-bj.ufileos.com/monitor/editalert001.png)

选择资源中点击添加资源按钮，选择要绑定的TiDB集群
![](https://tidb-doc.cn-bj.ufileos.com/monitor/editalert002.png)