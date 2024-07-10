# 性能数据

TiDB 可以通过水平扩容的方式提升性能，以下为TiDB在典型配置下的性能表现。

- 版本: v7.1.2
- 表: 32 * 1000万条数据
- 测试时间: 1200s
- Sysbench: v1.0.13

## 集群配置
| type	| config  | quantity | storage |
| ----- | ------  | -------- | ------- |
| TiDB	| 16C/32G | 2	     | 200     |
| TiKV	| 16C/64G | 3	     | 1000    |
| PD    | 4C/8G   | 3        | N/A     |

## oltp_point_select
![](https://tidb-doc.cn-bj.ufileos.com/utidb/oltppointselect.png)

## oltp_read_only

![](https://tidb-doc.cn-bj.ufileos.com/utidb/oltpreadonly.png)

## oltp_write_only

![](https://tidb-doc.cn-bj.ufileos.com/utidb/oltpwriteonly.png)

## oltp_read_write

![](https://tidb-doc.cn-bj.ufileos.com/utidb/oltpreadwrite.png)

## oltp_update_index

![](https://tidb-doc.cn-bj.ufileos.com/utidb/oltpupdateindex.png)

