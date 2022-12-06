# 参数配置

本文将阐述如何通过控制台修改TiDB实例参数。

## 进入管理页面

在产品主页中找到对应的实例， 点击“详情”按钮进入详情页面。

![](http://tidb-doc.cn-bj.ufileos.com/basic/instance.list.detail.button.png)

## 查看

切换到 “参数配置” 面板， 会自动列出所有的参数及当前配置

![](http://tidb-docs.cn-bj.ufileos.com/configure00.png)

## 修改

输入框中输入希望修改的参数，并点击提交

![](http://tidb-docs.cn-bj.ufileos.com/configure002.png)


## 参数列表

| 参数名| 默认值 | 范围值 | 是否需要重启 | 参数说明 | 
| --- | --------- | ----------- | ------ | ------- | 
|proxysql_mysql-max_connections|2048|1 ~ 1000000|否|所有用户总共的最大连接数|
|proxysql_max_connections|10000|1 ~ 100000|否|每个用户的最大连接数|
|tidb_gc|10m0s|[10m - 720h]|否|tikv_gc_life_time|
|tidb_txn-total-size-limit | 104857600 | [104857600 - 1099511627776] |是| txn-total-size-limit|
| tidb_max-index-length |3072|[3072 - 12288]|是|max-index-length|
