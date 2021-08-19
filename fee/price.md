# 计费

## 计费模式

UCloud TiDB Service 为用户提供serverless服务， 实行按小时后付费的计费模式。

## 计费内容

### TiDB 集群费用

具体收费内容如下：

| 类型  | 单价(元/小时/GB）| 组件|
| ------- | ------- | ------- | 
| 硬盘   | 0.004     | TiKV, Pump, TiFlash  |
| 内存   | 0.2    | TiKV, Pump, Drainer, TiFlash  |

### 备份数据存储费用

如果用户开启了备份功能，备份数据存储在用户的US3空间中，US3的费用由用户承担。
