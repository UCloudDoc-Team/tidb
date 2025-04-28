# 数据迁移

## 存量 MySQL 迁移到 TiDB 服务

[UDTS](https://docs.ucloud.cn/udts/type/mysql_source/mysql2tidb)  产品支持 MySQL(5.5/5.6/5.7/8.0) 到 TiDB 的全量数据迁移， 及增量数据同步。 可协助用户在不停机的情况下轻松将业务从MySQL 切换至 TiDB。

## 自建 TiDB 迁移到 TiDB 服务

[UDTS](https://docs.ucloud.cn/udts/type/tidb) 产品支持 TiDB 全量数据迁移至 TiDB服务。 用户在源TiDB开启Pump, Drainer 可进行数据增量同步。 UDTS与源端Pump, Drainer一起可协助用户在不停机的情况下轻松将业务从自建TiDB 切换至 TiDB 服务。

## 为 TiDB 服务建立 MySQL 从库

[UDTS](https://docs.ucloud.cn/udts/type/tidb) 产品支持 TiDB 全量数据迁移至 MySQL 数据库。 用户在TiDB服务上开启 [Binlog](https://docs.ucloud.cn/tidb/guide/utidb/binlog)可将数据增量同步至下游MySQL。 UDTS 与 TiDB Binlog服务一起可协助用户轻松建立MySQL从库。

## 为 TiDB 服务建立 TiDB 从库

[UDTS](https://docs.ucloud.cn/udts/type/tidb) 产品支持 TiDB 全量数据迁移至 TiDB 数据库。 用户在源TiDB服务上开启 [Binlog](https://docs.ucloud.cn/tidb/guide/utidb/binlog) 可将数据增量同步至下游TiDB。 UDTS 与 TiDB Binlog服务一起可协助用户轻松建立TiDB从库。
