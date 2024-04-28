# 如何使用TiFlash

## 简介
TiFlash 是 TiDB HTAP 形态的关键组件。开启TiFlash后可以更好的满足用户的分析型业务场景需求。

## 步骤一 开启TiFlash

点击按钮，选择TiFlash节点数，确定开启，确保TiFlash状态为“已开启”

![](http://tidb-doc.cn-bj.ufileos.com/tiflash/tiflashopen003.png)

![](http://tidb-doc.cn-bj.ufileos.com/tiflash/tiflashopen004.png)

![](http://tidb-doc.cn-bj.ufileos.com/tiflash/tiflashopen005.png)

## 步骤二 按表构建TiFlash副本

构建TiFlash副本

```
ALTER TABLE table_name SET TIFLASH REPLICA count;

count 表示副本数，0 表示删除。count数不超过已开启TiFlash节点数。
```

查看表同步进度

```
SELECT * FROM information_schema.tiflash_replica WHERE TABLE_SCHEMA = '<db_name>' and TABLE_NAME = '<table_name>';

查询结果中AVAILABLE 字段表示该表的 TiFlash 副本是否可用。1 代表可用，0 代表不可用。副本状态为可用之后就不再改变，如果通过 DDL 命令修改副本数则会重新计算同步进度。
PROGRESS 字段代表同步进度，在 0.0~1.0 之间，1 代表至少 1 个副本已经完成同步。
```
## 步骤三 使用TiFlash

同步完成后，TiDB 优化器会自动根据代价估算选择是否使用 TiFlash 副本。具体有没有选择 TiFlash 副本，可以通过 desc 或 explain analyze 语句查看，例如：

```
desc select count(*) from test.t;
+--------------------------+---------+--------------+---------------+--------------------------------+
| id                       | estRows | task         | access object | operator info                  |
+--------------------------+---------+--------------+---------------+--------------------------------+
| StreamAgg_9              | 1.00    | root         |               | funcs:count(1)->Column#4       |
| └─TableReader_17         | 1.00    | root         |               | data:TableFullScan_16          |
|   └─TableFullScan_16     | 1.00    | cop[tiflash] | table:t       | keep order:false, stats:pseudo |
+--------------------------+---------+--------------+---------------+--------------------------------+
3 rows in set (0.00 sec)
```

```
explain analyze select count(*) from test.t;
+--------------------------+---------+---------+--------------+---------------+----------------------------------------------------------------------+--------------------------------+-----------+------+
| id                       | estRows | actRows | task         | access object | execution info                                                       | operator info                  | memory    | disk |
+--------------------------+---------+---------+--------------+---------------+----------------------------------------------------------------------+--------------------------------+-----------+------+
| StreamAgg_9              | 1.00    | 1       | root         |               | time:83.8372ms, loops:2                                              | funcs:count(1)->Column#4       | 372 Bytes | N/A  |
| └─TableReader_17         | 1.00    | 1       | root         |               | time:83.7776ms, loops:2, rpc num: 1, rpc time:83.5701ms, proc keys:0 | data:TableFullScan_16          | 152 Bytes | N/A  |
|   └─TableFullScan_16     | 1.00    | 1       | cop[tiflash] | table:t       | time:43ms, loops:1                                                   | keep order:false, stats:pseudo | N/A       | N/A  |
+--------------------------+---------+---------+--------------+---------------+----------------------------------------------------------------------+--------------------------------+-----------+------+
```

- 官方文档

https://docs.pingcap.com/zh/tidb/v4.0/use-tiflash
