# 在 SQL Server 中将行组合成字符串

> 原文：[https://www.geeksforgeeks.org/combine-rows-into-string-in-sql-server/](https://www.geeksforgeeks.org/combine-rows-into-string-in-sql-server/)

假设我们需要从任何给定的列表中选择所有的数据。我们可以使用多个查询将 SQL Server 中的行组合成一个字符串。

## 示例-1

让我们假设我们下面有一张桌子命名为 `[geek_demo]`。

| FirstName | LastName | Deepak | Saini | 24300 | Delhi |
| --- | --- | --- | --- | --- | --- |

### 方法-1

在下面的例子中，我们将使用 `COALESCE` 函数合并行。

**查询连接 SQL Server 中的行：**

```sql
DECLARE @Names VARCHAR(MAX)  
SELECT @Names = COALESCE(@Names + ', ', '') + [FirstName] 
FROM [geek_demo]
SELECT @Names AS [List of All Names]
```

**输出：**

| List of all names |
| --- |
| Ankit, Barbita, Chetan, Dipka, Isa, Guxi, Mega, Parur. |

### 方法-2

在下面的例子中，我们也将组合姓氏行。

**查询连接 SQL Server 中的行：**

```sql
DECLARE @FirstNames VARCHAR(MAX)
DECLARE @LastNames VARCHAR(MAX)
SELECT @FirstNames = COALESCE(@FirstNames + ', ', '') + [FirstName] 
FROM [geek_demo]   
SELECT @LastNames = COALESCE(@LastNames + ', ', '') + [LastName] 
FROM [geek_demo] 
SELECT @FirstNames AS [List of All First Names],
            @LastNames AS [List of All Last Names]
```

**输出：**

| List of all names | List of all surnames |
| --- | --- |
| Ankit, Barbita, Chetan, Dipka, Isa, Guxi, Mega, Parur. | Puta, Duta, Jain, Saini, Sharma, Singer, Gauillard, Living Goddess. |

### 方法-3

在下面的例子中，我们也将连接姓氏行。

**查询连接 SQL Server 中的行：**

```sql
DECLARE @FirstNames VARCHAR(MAX)
DECLARE @LastNames VARCHAR(MAX)
SELECT @FirstNames = CONCAT(@FirstNames + ', ', '') + [FirstName] 
FROM [geek_demo]  
SELECT @LastNames = CONCAT(@LastNames + ', ', '') + [LastName] 
FROM [geek_demo]
SELECT @FirstNames AS [List of First All Names],
   @LastNames AS [List of All Last Names]
```

**输出：**

| Name list of all names | First name list of all surnames |
| --- | --- |
| Ankit, Barbita, Chetan, Dipka, Isa, Guxi, Mega, Parur. | Puta, Duta, Jain, Saini, Sharma, Singer, Gauillard, Living Goddess. |

### 方法-4

在下面的例子中，我们将使用 `STUFF` 函数结合两列（名字 & 姓氏）的行，并用于 `XML PATH`。

**查询连接 SQL Server 中的行：**

```sql
SELECT STUFF((
   SELECT ',' + SPACE(1) + [FirstName],
   ' ' + SPACE(1) + [LastName]
 FROM [geek_demo]
  FOR XML PATH(''), TYPE).value('.', 'VARCHAR(MAX)'), 1, 1, '')
AS [List Of All Names]
```

**输出：**

| name list |
| --- |
| Ankit Gupta, Babita Duta, Chetan Jain, Dipka Seni, Isha Sharma, Guxi Singh, Mega Gauillard, Parul Living Goddess. |

## 示例-2

让我们假设我们下面有一个名为 `"geek_demo1"` 的表。

| Name | Date of joining | Email |
| --- | --- | --- |
| Ankit | May 04th, 2018 | ankit@gfg.org |
| Babita | | deepak@gfg.org |
| Isha | May 24th, 2018 | isha@gfg.org |
| Kehu | July 17th, 2018 | megha@gfg.org |

### 方法-1

在下面的例子中，我们将使用 SQL Server 中的 `CONCAT` 函数将行组合成一个字符串。

**查询连接 SQL Server 中的行：**

```sql
DECLARE @Names VARCHAR(MAX)
DECLARE @Emails VARCHAR(MAX)
SELECT @Names = CONCAT(@Names + ', ', '') + [Name] 
FROM [geek_demo1]  
SELECT @Emails = CONCAT(@Emails + ', ', '') + [Email] 
FROM [geek_demo]  
SELECT @Names AS [List of All Names],
            @Emails AS [List of All Emails]
```

**输出：**

| List of all names | All e-mail lists |
| --- | --- |
| Ankit, Babita, Chetan, Dipka, Isha, Guxi, Mega, Parur. | ankit@gfg.org、babita@gfg.org、chetan@gfg.org、deepak@gfg.org、isha@gfg.org、khushi@gfg.org、megha@gfg.org、parul@gfg.org |

### 方法-2

在下面的示例中，我们将使用 `SPACE` 和 `FOR XML PATH` 组合 SQL Server 中的行。

**查询连接 SQL Server 中的行：**

```sql
SELECT STUFF((
  SELECT ',' + SPACE(1) + [Email]
  FROM [geek_demo]
  FOR XML PATH(''), TYPE).value('.', 'VARCHAR(MAX)'), 1, 1, '')
AS [List Of All Emails]
```

**输出：**

| All mailing lists |
| --- |
| ankit@gfg.org、babita@gfg.org、chetan@gfg.org、deepak@gfg.org、isha@gfg.org、khushi@gfg.org、megha@gfg.org、parul@gfg.org |