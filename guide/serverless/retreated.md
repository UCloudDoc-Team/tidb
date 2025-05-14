# 回档管理

Serverless版TiDB回档支持在GC范围内回档到新实例或回档到原实例功能，回档到新实例会在同项目同可用区下新建同配置实例，回档到原实例会重命名库表，选择时请注意。

在实例详情页中，点击“回档管理”菜单，进入回档管理页面。

![](https://tidb-doc.cn-bj.ufileos.com/backup-restore/retreated001.png)

## 回档至新实例

在回档管理页面中，点击“回档至新实例”按钮，选择待回档库表及回档目标时间，输入新实例名称，点击“确定”按钮。
![](https://tidb-doc.cn-bj.ufileos.com/backup-restore/retreated002.png)

回档任务创建后，可在回档管理页中查看当前回档任务状态

![](https://tidb-doc.cn-bj.ufileos.com/backup-restore/retreated004.png)

回档完成后，新实例会在实例列表中显示。

## 回档至原实例

在回档管理页面中，点击“回档至原实例”按钮，选择待回档库表及回档目标时间，点击“确定”按钮。

![](https://tidb-doc.cn-bj.ufileos.com/backup-restore/retreated003.png)

回档完成后，回档的库会重命名为原库名_bak_时间。
