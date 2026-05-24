# SQL Server | SERVERPROPERTY()

> 原文:[https://www.geeksforgeeks.org/sql-server-serverproperty/](https://www.geeksforgeeks.org/sql-server-serverproperty/)

SQL Server 提供了一个系统定义函数**SERVERPROPERTY(property name)**。

**SERVERPROPERTY():**SERVERPROPERTY()函数用于返回系统不同属性的信息或者所谓的实例信息。

**propertyname:** 该表达式包含关于所讨论的属性的信息，并返回相同的信息。

下面是 SERVERPROPERTY()函数提供的一些属性名称。除了上述属性，还有其他属性。

**1。MachineName:** 此属性名在 SERVERPROPERTY()函数中用作参数，用于查找运行 SQL Server 的机器/计算机的名称。

**语法:**

```sql
SELECT SERVERPROPERTY ('MachineName')

```

**例:**

![](img/d760fc80cd5180f99e979a7a3d0a51cf.png)

**输出:**

![](img/c4e060df626e4bf70beb2f4ed8586f0e.png)

**2。版本:**这个属性名在 SERVERPROPERTY()函数中作为参数，用来获取机器/计算机上安装的 SQL Server 的版本。

**语法:**

```sql
SELECT SERVERPROPERTY ('Edition')

```

**例:**

![](img/6518e3e9e154ecc5f17f33023b596f5b.png)

**3。instancedfaultdatapath:**这个属性名在 SERVERPROPERTY()函数中用作参数，用来查找数据文件的默认路径。

**语法:**

```sql
SELECT SERVERPROPERTY ('INSTANCEDEFAULTDATAPATH')

```

**例:**

![](img/a2e09dbe622426c599ccdd6e08b79e1a.png)

**4。INSTANCEDEFAULTLOGPATH:** 此属性名在 SERVERPROPERTY()函数中用作参数，以查找日志文件的默认路径。

**语法:**

```sql
SELECT SERVERPROPERTY ('INSTANCEDEFAULTLOGPATH')

```

**例:**

![](img/9d690a6d89c0d323b673b2f496863373.png)

**5。PRODUCTVERSION:** 此属性名在 SERVERPROPERTY()函数中用作参数，以获取有关正在使用的产品版本的信息。

**语法:**

```sql
SELECT SERVERPROPERTY (' PRODUCTVERSION')

```

**例:**

![](img/879119dcffb0ad58a4329ccd5bef1b32.png)

**6。BUILD CLVERSION:**此属性名在 SERVERPROPERTY()函数中用作参数，以获取有关微软版本的信息。NET 框架公共语言运行时。该框架用于构建 SQL Server 实例。

**语法:**

```sql
SELECT SERVERPROPERTY ('BUILDCLRVERSION')

```

**例:**

![](img/d69c6b5253787120acffb062a5a6f6c9.png)

**7。PROCESSID:** 此属性名在 SERVERPROPERTY()函数中用作参数，以获取 SQL Server 服务的进程 ID。

**语法:**

```sql
SELECT SERVERPROPERTY ('PROCESSID')

```

**例:**

![](img/6413f6cf11d537e259c491672b1ab4db.png)

**8。ResourceLastUpdateDateTime:** 此属性名在 SERVERPROPERTY()函数中用作参数，以获取有关资源数据库上次更新的信息，即资源数据库上次更新的日期和时间。

**语法:**

```sql
SELECT SERVERPROPERTY ('ResourceLastUpdateDateTime')

```

**例:**

![](img/28e7dd5e86acb0c570c47b810bc5dbd2.png)

**9。EditionID:** 此属性名在 SERVERPROPERTY()函数中用作参数，用于查找计算机/机器上正在安装的 SQL Server 的版本 ID。

**语法:**

```sql
SELECT SERVERPROPERTY ('EditionID')

```

**例:**

![](img/d0cfcc8911610d08ad2b54cecb082553.png)

**10。排序规则:**此属性名在 SERVERPROPERTY()函数中用作参数，用于查找计算机/机器上安装的 SQL Server 的排序规则。

**语法:**

```sql
select SERVERPROPERTY ('collation')
```

**示例:**

![](img/38140978fe4dcc371d81cf992e16c43b.png)

**注意:**要获取其他属性的信息，请参考[微软文档](https://docs.microsoft.com/en-us/sql/t-sql/functions/serverproperty-transact-sql)。