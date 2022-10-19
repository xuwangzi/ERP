#### 分工（第一版）

秦予唯 201250204 完成了用例图以及用例描述的第一版设计；建立线上项目 部署前后端

徐王子 201250200 修改用例描述

徐瀚林 201250008 完成系统用例图的第二版设计与修改；完成对md文件的编写

郑杰     201250201 完成用例描述最终版的编写

#### 分工（第二版）

秦予唯 201250204 修改了用例图、描述了库存快照、库存查看用例

徐王子 201250200 修改查看经营历程表系统顺序图，修改库存相关单据处理用例描述，完成对md文件的编写，git提交

徐瀚林 201250008 修改商品分类管理用例描述

郑杰     201250201 修改商品管理用例描写



#### 进销存用例系统：

![进销存用例系统](https://seec-homework.oss-cn-shanghai.aliyuncs.com/201250200-进销存用例系统.jpg)

#### 销售模块概念类图：

![销售模块概念类图](https://seec-homework.oss-cn-shanghai.aliyuncs.com/201250200-销售模块概念类图.jpg)

#### 查看经营历程表系统顺序图：

![查看经营历程表系统顺序图](https://seec-homework.oss-cn-shanghai.aliyuncs.com/201250200-查看经营历程表系统顺序图.png)



#### 商品管理用例描述

参与者：

​	库存管理人员，目标是在不增加工作量的情况下，快速完成商品数量的更改与查询

触发条件：

​	库存管理人员得到出库单或者入库单；库存管理人员已被授权，进入库存管理系统

前置条件：

​	货物商品已经经过分类管理，货物商品信息已经形成数据库可以调用

后置条件：

​	数据库相应更新

正常流程：

1. 库存管理人员进入商品管理界面，选中需要操作的商品（查询除外），选择操作类型（增、删、改、查），选择“增加”则跳转至第2步；选择“删除”则跳转至第4步；选择“修改”则跳转至第6步；选择“查询”则跳转至第8步；若操作结束则跳转至第10步

2. 系统显示“增加”界面，库存管理人员输入数量

3. 系统更改数据库，显示更改后的结果，待库存管理人员点击后返回第1步

4. 系统显示“删除”界面，库存管理人员输入数量

5. 系统更改数据库，显示更改后的结果，待库存管理人员点击后返回第1步

6. 系统显示“修改”界面，库存管理人员输入商品信息

7. 系统更改数据库，显示更改后的结果，待库存管理人员点击后返回第1步

8. 系统显示“查询”界面，库存管理人员输入需要查询的商品名称/商品编号

9. 系统显示查询结果，待库存管理人员点击后返回第1步

10. 库存管理人员点击“关闭”按钮

11. 商品管理界面关闭，系统返回至库存管理系统主界面

扩展流程：

2a.输入数量超过限定最大值

1. 系统显示错误提醒，同时拒绝输入。

2. 返回“增加”界面

4a.输入数量大于实际库存数量

​	1.系统显示错误提醒，同时拒绝输入。

​	2.返回“删除”界面

6a.修改的数据超过了限定数值区间

1. 系统显示错误提醒，同时拒绝输入

2. 返回“修改”界面

8a.查询结果无商品符合

​	1.系统提示“未找到相关的商品”

特殊要求：无

 

#### 库存盘点的用例描述

参与者：

​	库存管理人员目标是在不增加工作量的情况下，高效的、正确的完成当日库存快照的相关操作。

触发条件：

​	时间到达库存管理人员下班前30分钟

前置条件：

​	货物商品已经经过分类管理，货物商品信息已经形成数据库可以调用（当日库存数据已更新入库）

后置条件：

1. 数据库相应更新

2. 形成excel表单

正常流程：

  1.输入工号进入库存系统

  2.系统将当天所有商品的的名称，型号，库存数量， 库存均价（商品的平均进价），批次批号，生产日期，以及行号进行库存快照。

  3.系统显示库存快照并保存

扩展流程：

  2a.实际库房商品数量多于系统数据

  1.进行库存报溢，向系统库存减去商品，使得商品数量一致

  2b.实际库房商品数量少于系统数据

  1.进行库存报损，向系统库存加上商品，使得商品数量一致

  2c.输出表单

  ​	1.如有需要导出关于库存快照的数据形成excel表单

特殊要求：

  库存低于警戒值时向仓库管理员发送提示



库存查看的用例描述

参与者：

​	库存管理人员，目标是在不增加工作量的情况下，高效的、正确的完成库存查看的相关操作。

触发条件：

​	时间到达设定的时间段

前置条件：

​	货物商品已经经过分类管理，货物商品信息已经形成数据库可以调用，库存查看时间段已被设置，库存管理人员已经被识别和授权。

后置条件：

​	无

正常流程：

​	1.库存管理人员输入时间段

​	2.系统显示商品在此时间段的出入库数量、金额、商品信息、分类信息。

扩展流程：

​	1a.时间段有误

​		1.系统提示错误并拒绝输入

​	2a.实际库房商品数量多于系统数据

​    	1.进行库存报溢，向系统库存减去商品，使得商品数量一致

​    2b.实际库房商品数量少于系统数据

​        1.进行库存报损，向系统库存加上商品，使得商品数量一致

​    2c.库存数量合计

​        1.对库存数量进行合计计算并显示结果

特殊要求：

​     库存低于警戒值时向仓库管理员发送提示

​     库存需要定时定期查看，如有相关问题参照扩展流程处理





#### 商品分类管理用例描述

参与者：

​	库存管理人员，目标是为快速查看商品信息提供便利

触发条件：

​	库存管理人员已被授权，进入商品分类管理系统

前置条件：

​	库存管理人员已知目标商品的分类

后置条件：

​	数据库相应更新

正常流程：

1. 库存管理人员进入商品分类管理界面，点击界面中分类名称左侧的“+”以展开该分类，系统在下方展示其子类，库存管理人员可持续点击直至展开到最后，即为需要查看的商品；
2. 库存管理人员点击“添加分类”，输入分类名称，并选择该分类的父类（或者将其作为父类），以添加新的分类。
3. 库存管理人员右击任一分类，点击“添加商品”并输入商品信息，系统向该分类添加该商品
4. 库存管理人员右击任一分类，点击“删除”，系统删除该分类
5. 库存管理人员右击任一分类，点击“重命名”并输入新的名称，系统修改该分类名称
6. 库存管理人员右击任一商品，点击“删除”，系统从该分类中该商品移除
7. 库存管理人员点击“批量处理“并勾选任意分类，并执行3-6中的点击操作，系统对所有选中的分类或商品执行对应操作
8. 库存管理人员点击“关闭”，系统关闭分类管理界面

扩展流程

3a.必要商品信息（商品编号、名称等）空缺或格式有误

​	1.系统提示输入错误，并清空错误输入

​	2.库存管理人员重新输入对应信息

5a.分类名称格式有误

​	1.系统提示输入错误，并清空错误输入

​	2.库存管理人员重新输入对应信息

特殊要求：无





# 库存相关单据处理用例描述

#### 库存赠送单、报溢单、报损单处理用例描述

参与者：

​	库存管理人员，目标是在不增加工作量的情况下，高效的、正确地处理库存赠送单、报溢单、报损单处理。

触发条件：

​	库存管理人员已被授权，进入库存赠送单、报溢单、报损单的处理系统

前置条件：

​	库存管理人员已知此次单据需要填写的完整信息。

​	库存赠送单：实际库存中需要进行赠送的商品的种类和数量。

​	库存报溢单：实际库存中多出商品的种类和数量。

​	库存报溢单：实际库存中缺少商品的种类和数量。

后置条件：

​	数据库相应更新

​	形成excel表格

正常流程：

1. 库存管理人员进入库存赠送单、报溢单、报损单的处理系统，点击界面中的“填写库存赠送/报溢/报损表单”，进入库存赠送/报溢/报损表单的填写页面。

2. 库存管理人员右击“单据类型”一栏中的“库存赠送单”或“库存报溢单”或“库存报损单”，确定单据类型。

3. 库存管理人员逐一填写单据信息。

   ​	库存赠送单：实际库存中需要进行赠送的商品的种类和数量。

   ​	库存报溢单：实际库存中多出商品的种类和数量。

   ​	库存报溢单：实际库存中缺少商品的种类和数量。

4. 库存管理人员右击单据填写界面底部的“重新填写”，系统从目前表单中的所有已填写信息清除。

5. 库存管理人员右击单据填写界面底部的“确认并提交”，系统保存该表单，并上传至数据库进行库存数据的修改。

6. 库存管理人员点击“关闭”，系统关闭分类管理界面。

扩展流程

1a.必要单据信息（单据类型）未进行勾选

​	1.系统提示“请选择单据类型”，并使“填写库存赠送/报溢/报损表单”按键无效

​	2.库存管理人员勾选单据类型

​	3.系统重新开放“填写库存赠送/报溢/报损表单”按键功能

3a.必要单据信息（商品的种类和数量等）空缺或格式有误

​	1.系统提示输入错误，并清空错误输入

​	2.库存管理人员重新输入对应信息

5a.必要单据信息（商品的种类和数量等）空缺或格式有误

​	1.系统提示输入错误，清空错误输入，并使“确认并提交”按键无效

​	2.库存管理人员重新输入对应信息

特殊要求：无

#### 库存报警单处理用例描述

参与者：

​	库存管理人员，目标是在不增加工作量的情况下，高效的、正确地处理库存报警单。

触发条件：

​	库存管理人员已被授权，进入库存报警单的处理系统。

​	同时，库存数量低于警戒数量。

前置条件：

​	库存管理人员已设置警戒数量的值。

后置条件：

​	形成excel表格

正常流程：

1. 库存数据更新之后，库存报警单的处理系统检测到库存数量低于警戒数量。
2. 库存报警单在1分钟内，向库存管理人员发送库存报警信息。

扩展流程

2a.库存管理人员未被授权进入库存报警单的处理系统。

​	1.系统显示异常“ERROR：库存管理人员未被授权”

​	2.系统将异常信息挂起，等到有库存管理人员被授权后，重新发送库存报警信息

2b.库存报警单的处理系统无法联系上库存管理人员（如库存管理人员请假或者已下班）。

​	1.系统显示异常“ERROR：无法联系库存管理人员”

​	2.系统将异常信息挂起，等到系统能够联系库存管理人员后，重新发送库存报警信息

特殊要求：无

#### 入库单、出库单处理用例描述

参与者：

​	库存管理人员，目标是在不增加工作量的情况下，高效的、正确地处理入库单、出库单。

触发条件：

​	库存管理人员已被授权，进入入库单、出库单的处理系统

前置条件：

​	库存管理人员已知此次入库的完整信息

后置条件：

​	数据库相应更新

​	形成excel表格

正常流程：

1. 库存管理人员进入入库单、出库单的处理系统，点击界面中的“填写入库/出库表单”，进入入库/出库单的填写页面。

2. 库存管理人员右击“单据类型”一栏中的“入库单”或“出库单”，确定单据类型。

3. 库存管理人员逐一填写单据信息。

   入库单包含时间、操作员、入库类型（进货/买家退货）、这批商品的具体信息；

   出库单包含时间、操作员、出库类型（减库存/销售）、这批商品的具体信息。

4. 库存管理人员右击单据填写界面底部的“重新填写”，系统从目前表单中的所有已填写信息清除。

5. 库存管理人员右击单据填写界面底部的“确认并提交”，系统保存该表单，并上传至至总经理进行审批。

6. 库存管理人员点击“关闭”，系统关闭分类管理界面。

扩展流程

1a.必要单据信息（单据类型）未进行勾选

​	1.系统提示“请选择单据类型”，并使“填写入库/出库表单”按键无效

​	2.库存管理人员勾选单据类型

​	3.系统重新开放“填写入库/出库表单”按键功能

3a.必要单据信息（时间、操作员、入/出库类型、这批商品的具体信息等）空缺或格式有误

​	1.系统提示输入错误，并清空错误输入

​	2.库存管理人员重新输入对应信息

5a.必要单据信息（时间、操作员、入/出库类型、这批商品的具体信息等）空缺或格式有误

​	1.系统提示输入错误，清空错误输入，并使“确认并提交”按键无效

​	2.库存管理人员重新输入对应信息

特殊要求：无
