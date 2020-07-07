# 参数配置调整

本文将阐述如何通过控制台修改TiDB实例参数,陆续会新增可修改配置项。

进入实例 详情-参数配置

![](http://tidb-docs.cn-bj.ufileos.com/configure00.png)

输入框中输入希望修改的参数，并点击提交

![](http://tidb-docs.cn-bj.ufileos.com/configure002.png)

| 参数名| 默认值 | 范围值 | 是否需要重启 | 参数说明 | 
| --- | --------- | ----------- | ------ | ------- | 
|proxysql_mysql-max_connections|2048|1 ~ 1000000|否|mysql最大连接数|
|proxysql_max_connections|10000|1 ~ 100000|否|mysql user最大连接数|
