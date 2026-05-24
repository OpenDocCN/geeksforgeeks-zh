# MySQL 数据库文件

> 原文: [https://www.geeksforgeeks.org/mysql-database-files/](https://www.geeksforgeeks.org/mysql-database-files/)

每当 MySQL 数据库安装完成时，所有与数据库相关的数据和元数据都存储在一个文件夹中。这是实际的数据库模式，其中包含一些值。让我们对此进行更多的探索。

## 文件扩展名

文件扩展名如下:

*   `.frm` – 这是包含表的模式或定义的文件的扩展名。
*   `.myd` – 这是包含 MyISAM 表数据的文件的扩展名。
*   `.myi` – 这是包含 MyISAM 表索引的文件的扩展名。

在 `MySQL Server 5.5/data/MySQL` 文件夹里面，有些文件是 `*.frm`、`*.MYD` 和 `*.MYI`，其中星号是实际的表名。如果使用 MyISAM 引擎，数据文件夹会包含上述所有文件，否则在 InnoDB 的情况下，文件夹包含 `.frm` 文件。

这些数据库文件用于备份目的，以保护数据库的某些迁移或升级的模式、数据和索引。Windows 和 Linux 的 MySQL 的配置文件分别是 `my.ini` 和 `my.conf`。

窗口的路径:

```
C:\Program Files\MySQL\MySQL Server 5.5\my.ini
```

在 `my.ini` 文件中，如果我们搜索关键字 `basedir`，就可以得到 MySQL 服务器安装的路径。

同理，如果我们搜索关键字 `datadir`，就可以得到数据库根目录的路径。除此之外，MySQL 服务器还创建或使用许多其他文件来执行各种活动。其中一些如下。

## 配置文件

*   `my.cnf`:
    这是一个 MySQL 数据库配置文件。这是 MySQL 服务器的主要配置文件。它在安装完成的根目录中可以找到。在这个文件中，用户可以找到数据文件夹的位置。配置文件的默认位置是 `/etc/my.cnf`。其他与 MySQL 兼容的文件格式有 `.ibc`、`.tmd`、`.rul`、`.cnf`、`.ddl`、`.ibd`、`.mysql`、`.sql`、`.opt`。根据表的类型，表存储在具有这些扩展名的文件中。

*   `db.opt`:
    每当使用 MySQL 命令创建或更改数据库时，数据库的特性都存储在名为 `db.opt` 的文本文件中。

## 其他数据库文件

*   `.ibd`:
    这些是扩展名为 `*.ibd` 的文件，用于存储 MySQL InnoDB 表的数据和索引。这种类型的文件由 MySQL InnoDB 软件创建或使用，并与之关联。

*   `.sock`:
    所有 MySQL 数据库连接都由一个称为套接字文件的特殊文件管理。这个名为 `mysqld.sock` 的套接字文件由 MySQL 服务自动创建，有助于在不同进程之间进行通信。

*   Pid file:
    MySQL 服务器的进程 ID 被写入此类文件。默认将是 MySQL 服务器的主机名。

*   `.db`:
    这些是扩展名为 `.db` 的文件，用于存储 BerkeleyDB 存储引擎的数据和索引。

*   error log:
    错误日志文件在应用程序故障排除中确实起着重要作用。这些是 MySQL 错误日志文件，将提供服务器中 MySQL 故障的确切原因或信息。这有效地帮助了对 MySQL 服务器中出现的任何错误问题进行调试。默认情况下，它会将错误记录在 `hostname.err` 文件中。

*   Slow Query Log:
    慢查询日志文件包含所有“慢”的 SQL 查询。应用程序的性能下降是因为 MySQL 查询完成所需的时间比预期结果长。因此，这有助于监控慢查询，从而改进查询以获得更高的性能。

*   general query log:
    通用查询日志文件提供所有常规详细信息，如服务器启动或结束时间、上下线详细信息、连接或断开连接详细信息等。它通过 `log[=filename]` 启用。默认情况下，MySQL 将为条目创建 `hostname.log`。

*   binary log files:
    二进制日志文件包含与任何表创建或对 MySQL 服务器进行的数据修改相关的详细信息。它还包含有关 MySQL 语句所花费的时间、服务器状态、错误代码、用于维护日志文件的元数据等信息。这通过 `-log-bin[=basename]` 选项启用。默认情况下，它是服务器的主机名。

*   `.index`:
    为了监控使用了哪些二进制日志文件，会创建一个二进制日志索引文件，其中包含所有二进制日志文件的名称。它通过 `–log-bin-index[=filename]` 启用，否则基本名将是带有 `.index` 扩展名的二进制日志文件。默认情况下，中继日志索引文件名是 `host_name-relay-bin.index`。

*   `.TMD`:
    这些是由 MySQL 服务器在修复操作期间创建的中间数据库文件。此文件包含有关数据库恢复的信息。这些文件也可能由其他一些 MySQL 数据库操作创建。

*   TRG and TRN Files:
    TRG 文件是触发器参数文件，TRN 文件是触发器命名空间文件。在 MySQL 服务器中，每当定义触发器时，定义都存储在名为 `tablename.TRG` 的文本文件中。它包含多个事件的触发器，例如 MySQL 中 `INSERT`、`UPDATE` 或 `DELETE` 操作的 `BEFORE` 或 `AFTER`。

*   `.ARZ`, `.ARM` and `.ARN` files:
    表数据和表元数据文件的扩展名分别是 `.ARZ` 和 `.ARM`。`.ARN` 文件是优化过程中的优化文件。这些文件与归档存储引擎相关。

*   `.ARZ`:
    ARZ 文件是归档表的元数据文件。具有此扩展名的文件存储表的数据。这些文件包含在由 MySQL 的 `mysqlbackup` 命令创建的备份中。