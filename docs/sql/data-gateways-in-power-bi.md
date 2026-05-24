# 电力商业智能中的数据网关

> 原文:[https://www.geeksforgeeks.org/data-gateways-in-power-bi/](https://www.geeksforgeeks.org/data-gateways-in-power-bi/)

**先决条件–**[电力 BI](https://www.geeksforgeeks.org/power-bi-vs-tableau-top-5-key-differences-that-you-should-know/)

power BI 的主要目标是构建仪表板并保持数据最新，并确保在每个时间实例持续提取数据，以便跟踪每个时间实例的变化。
我们可以将 Power BI 集成到多个数据库中，例如–

1.  文件
2.  数据库ˌ资料库
3.  动力平台
4.  蔚蓝的

我们需要一个网关将 Power BI 服务连接到数据源，我们可以使用两个网关来实现这一点–

1.  个人网关
2.  内部数据网关

**个人网关:**
用于个人使用，连接数据库不需要任何组织的凭据。任何人都可以设置个人网关，并使用它来刷新数据，配置数据，并将其安装在个人机器上。

**个人网关的关键特性–**

1.  仅适用于强大的商业智能云服务。
2.  从给定数据源导入数据并设置计划刷新。
3.  作为非计算机管理员用户的应用程序运行。
4.  仅使用您的登录凭据作为单个用户运行。

**如何获得 Power BI 个人网关？**

1.  点击右上角**“下载图标”**。
2.  从下拉菜单中点击“**数据网关”**。
3.  您将在 Power BI 页面上看到不同类型的网关，该页面将在新选项卡上打开。
4.  可以点击**“下载网关”**选项下载。
5.  选择**“个人网关”**继续安装。
6.  安装后，我们可以使用 windows 身份验证方法连接到数据库服务。

**内部数据网关:**
这是一种付费服务，主要与组织的凭据一起用于连接数据库。用户应该来自同一个组织来设置网关并在上面工作。

**个人网关的关键特性–**

1.  与 power BI 云服务、PowerApps、Azure 逻辑应用程序、微软 Flow 合作。
2.  从给定数据源导入数据并设置计划刷新。
3.  提供对多个用户的访问以及对每个数据源的访问控制。
4.  支持直接查询到 SQL Server。
5.  监控和审计服务。

**如何获得 Power BI 企业网关？**

1.  点击右上角**“下载图标”**。
2.  从下拉菜单中点击“**数据网关”**。
3.  您将在 Power BI 页面上看到不同类型的网关，该页面将在新选项卡上打开。
4.  可以点击**“下载网关”**选项下载。
5.  选择**“企业网关”**继续安装。
6.  登录时，在出现提示时输入电子邮件标识，并插入您用于登录 Power BI 帐户的相同电子邮件标识。
7.  这将成为网关的管理员。
8.  您可以稍后添加其他管理员帐户。
9.  要配置网关，请插入网关名称、恢复密钥，然后单击完成。

**个人和内部网关对比研究:**

<figure class="table">希望生成自己报告的个人。 T42】无监控

|  | **Personal gateway** | **Internal gateway** |
| **Target personnel** | Business intelligence administrators who want to develop gateways for organizations. |
| **Usage** | analyst | BI administrators and developers |
| **Monitoring** | The organization can monitor accounts. |
| **Supported services** | 仅限电力商业智能 | 电力商业智能、电力应用、微软流量、蔚蓝逻辑应用 |

</figure>