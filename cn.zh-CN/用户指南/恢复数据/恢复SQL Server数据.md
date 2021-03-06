# 恢复SQL Server数据 {#concept_o52_hlx_52b .concept}

如果拥有RDS for SQL Server实例的数据备份，可以通过备份恢复的方式实现数据修复。

您可以通过多种方式恢复RDS for SQL Server实例的数据。

-   [恢复到已有实例](#)
-   [恢复到全新实例](#)
-   [通过临时实例恢复到主实例](#)

## 注意事项 {#section_qbn_ygz_xfb .section}

若数据量较大，花费的时间可能较长，请耐心等待。

## 恢复到已有实例 {#section_huifu .section}

您可以将实例的全量备份集恢复到您已有的实例，包括当前实例本身。可以恢复实例的所有数据库或者部分数据库。

本功能适用于RDS for SQL Server 2012/2016实例。

**操作步骤**

1.  登录[RDS管理控制台](https://rds.console.aliyun.com/)。
2.  选择备份集所属实例所在的地域。

    ![地域截图](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/7882/155254908137169_zh-CN.png)

3.  单击备份集所属实例的ID。
4.  在左侧导航栏中，选择**备份恢复**。
5.  在页面右上角，单击**数据库恢复**。
6.  （仅高可用系列需要执行本步骤）选择**恢复到已有实例**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17685/155254908210029_zh-CN.png)

7.  设置以下参数，然后单击**确定**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17685/155254908210031_zh-CN.png)

    **说明：** 若有相同数据库名存在，需要修改恢复后库名。

    |参数|说明|
    |--|--|
    |还原方式|对于恢复到已有实例，仅支持按备份集进行恢复。|
    |备份集|选择您要恢复的备份集。系统默认显示当前实例下的所有全量备份集。

|
    |目标实例名|选择要将备份集恢复到哪个实例。系统默认显示属于当前阿里云账号的、在当前地域的、与当前实例版本相同的实例，包括当前实例。

**说明：** 显示的目标实例较多时，可以使用搜索框进行筛选。

|
    |需恢复的数据库|     1.  选择要恢复的数据库。系统默认显示且勾选了备份集中的所有数据库。
        -   如果要恢复整个实例的数据，请保持勾选所有数据库。
        -   如果要恢复指定数据库，请只勾选部分数据库。
    2.  设置恢复后的数据库名。系统默认使用备份集中的数据库名。

**说明：** 恢复后的数据库名不能与目标实例中已有的数据库名相同。

 |


## 恢复到全新实例 {#section_l2n_r4x_52b .section}

本功能原名为克隆实例，用于将实例的历史备份恢复到一个全新的实例。您可以按时间点或者备份集恢复数据。按备份集恢复时，可以恢复备份集中的所有数据库或者部分数据库。

费用：需要新建实例，费用与新购实例相同。

本功能适用于RDS for SQL Server 2012/2016/2017实例。

**操作步骤**

1.  登录[RDS管理控制台](https://rds.console.aliyun.com/)。
2.  选择实例所在的地域。

    ![地域截图](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/7882/155254908137169_zh-CN.png)

3.  单击实例的ID。
4.  在左侧导航栏中，选择**备份恢复**。
5.  在页面右上角，单击**数据库恢复**，在弹出的对话框中，选择**恢复到全新实例**。
6.  在弹出的页面中，选择新实例的计费方式：**包年包月**或**按量付费**。
7.  设置新实例的参数。

    |参数名称|说明|
    |----|--|
    |**还原方式**|按时间点或备份集来复制数据。|
    |**还原时间**|若还原方式选择的是**按时间点**，则有该参数。选择所需复制数据所在的时间点。|
    |**备份集**|若还原方式选择的是**按备份集**，则有该参数。选择要复制的备份集。|
    |**数据库**|     -   **全部**：恢复备份集中的所有数据库。
    -   **部分**：恢复备份集中的部分数据库。如果选择此项，需要将要恢复的数据库添加到右侧。
 |
    |**系列/可用区/规格/存储空间/网络类型/购买时长**|关于这些参数的说明，请参见[创建实例](../../../../../intl.zh-CN/RDS for SQL Server 快速入门/创建RDS for SQL Server实例.md#)。|
    |**购买量**|设置购买数量，批量创建克隆实例。单次最多可以创建5个克隆实例。|

8.  单击**立即购买**。
9.  确认订单信息，并勾选**关系型数据库RDS服务条款**。
10. 单击**去支付**，根据提示完成支付。

## 通过临时实例恢复到原实例 {#section_ejq_2yz_52b .section}

本功能适用于以下RDS for SQL Server实例：

-   SQL Server 2012企业版基础系列
-   SQL Server 2012/2016 Web版基础系列
-   SQL Server 2008 R2

具体操作请参见[通过临时实例恢复到主实例](intl.zh-CN/用户指南/恢复数据/通过临时实例恢复SQL Server数据.md)。

