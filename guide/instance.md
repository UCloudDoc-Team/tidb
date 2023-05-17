# 实例

## 创建TiDB实例

- 点击【创建实例】

![](http://tidb-doc.cn-bj.ufileos.com/basic/TiDB-create.png)

- 选择基础配置版本

根据需要选择配置版本，默认选择旗舰版。 不同版本的说明请参考[实例类型](https://docs.ucloud.cn/tidb/introduction/instancetype)。

旗舰版支持设置资源使用上限。可以在创建时选择，创建完成后也可进行调整。

![](http://tidb-doc.cn-bj.ufileos.com/basic/instence_type20230517.png)

- 网络设置

选择实例所属VPC及子网， 系统会默认选择列表中的第一项。

- 指定IP及端口创建实例

默认情况下系统会自动分配一个IP及一个端口用来访问数据库。 如果用户需要指定IP及端口， 请选中“指定IP及端口”框， 页面会增加显示IP及端口输入框， 在对应的输入框中输入指定内容即可。

> 端口范围 1~65535, 禁用端口: 22,25,111,7002,7041,8080,9100,9115
 
![](http://tidb-doc.cn-bj.ufileos.com/basic/create_fixed_ip_port.png)

- 容灾设置

提供“同可用区”、“跨可用区”两种容灾类型。 “同可用区”指所有组件节点都部署在同一个可用区（同类服务的不同节点部署在不同的服务器上），有较好的性能。 “跨可用区”指同类服务的不同节点部署在至少三个以上的可用区， 可保证可用区级故障发生时服务继续可用， 但性能比“同可用区”有所下降。 “跨可用区”类型只有部分地域提供， 所有地域默认创建“同可用区”实例。

![](http://tidb-doc.cn-bj.ufileos.com/basic/create_dttype.png)

- 管理设置

可以为实例自定义实例名称， 系统默认会生成“TiDB”。 设置管理员(root)密码， 可以自行输入， 也可以点击“随机生成”。

- 立即购买

当所有信息完整以后， 点击右上角的“立即购买” 按钮来创建实例。

## 查看TiDB实例列表

进入产品主页， 会默认列出当前地域的实例列表。 

![](http://tidb-doc.cn-bj.ufileos.com/basic/instance.list1.png)


## 查看TiDB实例详情

进入产品主页， 会默认列出当前地域的实例列表。 找到实例，点击操作栏中的“详情”按钮进入详情页面。

![](http://tidb-doc.cn-bj.ufileos.com/basic/instance.list.detail.button.1.png)

详情页面左侧会显示实例的基础信息等内容，可以在页面左侧进行资源上限调整， 右侧会展示监控信息，监控项有数据量，QPS，TPS，内存使用量等。

![](http://tidb-docs.cn-bj.ufileos.com/config001.png)

## 删除TiDB实例

进入产品主页， 会默认列出当前地域的实例列表。 找到需要删除的实例，点击操作栏中的“删除实例”按钮进入删除确认页面。

![](http://tidb-doc.cn-bj.ufileos.com/basic/delete_button.png)

![](http://tidb-docs.cn-bj.ufileos.com/delete001.png)


