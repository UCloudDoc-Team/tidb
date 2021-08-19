# TiDB定价

## 1. 计费方式

UCloud TiDB Service 为用户提供serverless服务， 实行按小时计费方式。

## 2. 计费内容

### TiDB 集群费用

具体收费内容如下：

| 类型  | 单价(元/小时/GB）| 组件|
| ------- | ------- | ------- | 
| 硬盘（NVME）   | 0.004     | TiKV, Pump, TiFlash  |
| 内存   | 0.2    | TiKV, Pump, Drainer, TiFlash  |

### 备份数据存储费用

对于同可用区实例， 如果用户开启了备份功能，备份数据存储在用户的US3空间中，US3的费用由用户承担。
