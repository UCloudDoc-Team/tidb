# 实例

## 创建TiDB实例

- 点击【创建实例】

![](http://tidb-doc.cn-bj.ufileos.com/basic/TiDB-create.png)

- 完善信息

根据信息选择实例类型，VPC 和子网，为保证IP可用数量，我们暂时仅支持子网掩码位数小于22的子网。

![](http://tidb-doc.cn-bj.ufileos.com/basic/create002.png)

- 内存限制
 
为了满足小数据量用户控制内存使用上限的需求， 我们提供限制TiKV内存的选项。 默认不做限制， 按需使用。 当开启限制功能后，存储(TiKV)节点的总内存使用量会被限制在60G/30G的范围内。

![](http://tidb-doc.cn-bj.ufileos.com/basic/create003.png)

## 删除TiDB实例

![](http://tidb-docs.cn-bj.ufileos.com/delete001.png)

## 查看TiDB实例监控

目前的监控有数据量，QPS，TPS，内存使用量。

内存使用可根据用户实际使用进行弹性扩容。


![](http://tidb-docs.cn-bj.ufileos.com/config001.png)

