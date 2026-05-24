# 使用 T-SQL 在 SQL Server 中配置 SQL 作业

> 原文:[https://www . geesforgeks . org/configure-SQL-jobs-in-SQL-server-use-t-SQL/](https://www.geeksforgeeks.org/configure-sql-jobs-in-sql-server-using-t-sql/)

在本文中，我们将学习如何使用 T-SQL 在 SQL Server 中配置 SQL 作业。此外，我们将详细讨论使用 T-SQL 的 SQL Server 中的 SQL 作业的参数。我们一个一个来讨论。

**简介:**
SQL Server Agent 是一个用于数据库任务自动化的组件。例如，如果我们只需要在非营业时间对生产服务器执行索引维护。因此，我们创建了一个运行索引维护的 SQL Server 作业，并将其安排在“非工作”时间。当我们安装 SQL Server 时，SQL Server 代理被禁用。因此，首先我们将启用它并手动启动它。然后，我们将使用 SQL Server 管理工作室和 MSDB 数据库的系统存储过程来配置 SQL Server 作业。因此，本文解释了如何使用 MSDB 数据库的系统存储过程创建 SQL Server 作业。

**MSDB 数据库的系统存储过程:**
SQL Server 使用的如下。

**查询-1 : sp_add_job :**
该过程用于创建新作业。如果成功，它将返回@job_id。以下参数适用于以下情况。

*   **@ job _ name–**
    这是一个唯一的作业名。
*   **@ enabled–**
    作业已启用或禁用。创建作业后，可以将参数值设置为 1 来启用作业。
*   **@ notify _ level _ event log–**
    此参数用于在 Windows 事件查看器中写入 SQL 作业的状态。

<figure class="table">

| 价值 | 描述 |
| --- | --- |
| Zero | 作业的结果不会写入事件日志。 |
| one | 如果作业成功执行，结果将被写入事件查看器 |
| 2(默认值) | 如果作业失败，结果和错误消息将被写入事件查看器。 |
| three | 作业的结果被写入事件查看器。 |

</figure>

*   **@ notify _ level _ email–**
    它会根据工作结果发送邮件。参数的有效值与@notify_level_eventlog 参数值相同。
*   **@ notify _ level _ page–**
    此参数用于发送 SQL 作业结果的寻呼机通知。参数的有效值与@ notiify _ level _ eventlog 参数值相同。
*   **@ delete _ level–**
    该参数用于完成后删除作业。在这种情况下，参数的值应该是
*   **注意–**
    默认值为 0；然后，它不会在完成后删除作业。
*   **@ category _ level–**
    该参数表示作业类别值。默认值为空。
*   **@ owner _ log in _ name–**
    该值为域名或作业所有者的 SQL 登录名。

**Query-2:Sp _ add _ jobserver:**
对于 SQL 作业执行，它指定目标服务器。它接受以下论点。

*   **@ job _ id–**
    在 SQL 作业中，它标识唯一的值，是一个 UNIQUEIDENTIFIER。其默认值为空。
*   **@ job _ name–**
    在 SQL 作业中，此参数指定作业的名称。
*   **@ server _ name–**
    它是要运行 SQL 作业的服务器的名称。默认参数值可以是本地服务器(local)或目标服务器主机名。

**查询-3: sp_add_jobstep :**
该存储过程用于在 SQL Job 中添加作业步骤。这些过程使用如下参数。

*   **@ job _ name–**
    要添加步骤的作业的名称。它是一个 SYSNAME，默认值为空。
*   **@ step _ name–**
    该步骤的名称。这是一个以空值为默认值的 SYSYNAME。
*   **@ step _ id–**
    作业步骤的顺序 ID。这是一个没有间隙的增量数。它是一个 INT 值，默认值为空。
*   **@ cmdexec _ success _ code–**
    该值由 CmdExec 子系统返回。它指示命令执行是否成功。代码为 int 值，默认值为 0。
*   **@ on _ success _ action–**
    该值表示作业步骤成功完成后应执行的操作。这些值可以是以下任意值:

<figure class="table">

| 价值 | 描述 |
| --- | --- |
| one | 辞掉工作，成功归来。 |
| Two | 退出作业并返回失败。 |
| three | 转到下一个作业步骤 |
| four | 转到 on_success_step_id 的步骤 id |

</figure>

*   **@ on _ fail _ action–**
    指定作业步骤失败时要执行的操作。它是一个 INT 值，默认值为空。
*   **@ retry _ 尝试–**
    指定作业步骤失败后的重试次数。它是一个 INT 值，默认值为空。
*   **@ retry _ interval–**
    设置两次 SQL 作业步骤失败尝试之间的时间间隔。它是一个 INT 值，默认值为空。
*   **@ Subsystem–**
    指定 SQL Server 代理用来执行命令的子系统的名称。有效值如下:

<figure class="table">

| 子系统值 | 描述 |
| --- | --- |
| CmdExec 文件(*。exe，*。蝙蝠) | 操作系统命令或可执行文件 |
| 分析查询 | SQL Server 分析服务查询，例如，DMX MDX |
| ANALYSISQUERY | SQL Server 分析服务命令，例如 XMLA。 |
| SSIS | SQL Server 集成服务包。 |
| PowerShell | 脚本上的 PowerShell 命令。 |
| T-SQL | 查询或存储过程 |
| 分配 | SQL Server 复制分发服务器代理。 |
| 快照 | SQL Server 复制快照代理。 |
| 成功了 | SQL Server 复制日志读取器代理。 |
| QueueReader | SQL Server 复制队列读取器。 |

</figure>

*   **@ command–**
    指定 SQL Server 代理服务应该通过子系统执行的命令。数据类型为 varchar(max)，默认值为 NULL。
*   **@ Database _ name–**
    指定要运行命令的数据库的名称。当您使用 SQL Server 代理运行一个 T-SQL 脚本时，此参数非常有用。

**查询-4:Sp_add_jobschedule :**
存储过程用于创建 SQL 作业计划。此过程使用以下参数。

*   **@ Job _ name–**
    指定 SQL 作业的名称。将为@job_name 参数中指定的 SQL 作业制定计划。
*   **@名称–**
    日程的名称。数据类型为 varchar，默认值为 NULL。
*   **@ enabled–**
    设置 1 以启用计划，或设置 0 以禁用计划。
*   **@ freq _ type–**
    表示执行 SQL 作业的时间。参数的数据类型为 INT，默认值为 0。有效值为以下任何一项 **g :**

<figure class="table">

| 价值 | 描述 |
| --- | --- |
| one | 该作业将只执行一次。 |
| four | 每天地；天天地 |
| eight | 一周的 |
| Sixteen | 每月 |
| Sixty-four | 当 SQL Server 代理服务启动时执行作业。 |
| One hundred and twenty-eight | 当服务器空闲时执行 SQL 作业。 |

</figure>

*   **@ freq _ interval–**
    表示执行 SQL 作业的日期。数据类型为 INT，默认值为 0。该值取决于@freq_type 参数中指定的值。有效值为以下任意值:

<figure class="table">

| 价值 | 对作业计划的影响 |
| --- | --- |
| 1(一次) | 将不使用 **@Freq_interval** 。 |
| 4(每日) | 每隔 **@freq_interval** 天 |
| eight | @Freq_interval 的值可以是以下任意值。1 =周日2 =星期一4 =星期二8 =星期三16 =星期四32=星期五64=周六 |
| Sixteen | 在每月的@Freq_interval 日运行作业 |
| Sixty-four | 将不使用 **@Freq_interval** 。 |
| One hundred and twenty-eight | 将不使用 **@Freq_interval** 。 |

</figure>

*   **@ freq _ subday _ type–**
    指定 freq_subday_interval 的单位。数据类型为 INT，默认值为 NULL。
*   **@ active _ start _ date–**
    设置想要开始作业执行的日期。数据类型是 INT，它没有默认值。日期格式为 YYMMDD。该值必须大于或等于 19900101。
*   **@ active _ end _ date–**
    指定停止作业执行的日期。数据类型为 INT，没有默认值。日期格式为 YYMMDD，值必须大于或等于 19900101。
*   **@ active _ start _ time–**
    指定要开始作业执行的时间。数据类型为 INT，没有默认值。时间格式为 HHMMSS。
*   **@ active _ end _ time–**
    指定要停止作业执行的时间。数据类型为 INT，没有默认值。时间格式为 HHMMSS。