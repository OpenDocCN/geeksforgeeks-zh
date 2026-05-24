# 在 SQL Server 中将行组合成字符串

> 原文:[https://www . geesforgeks . org/combine-row-in-string-SQL-server/](https://www.geeksforgeeks.org/combine-rows-into-string-in-sql-server/)

假设我们需要从任何给定的列表中选择所有的数据。我们可以使用多个查询将 SQL Server 中的行组合成一个字符串。

**例-1 :**
让我们假设我们下面有一张桌子命名为**【geek _ demo】**【isha】【Sharma】

| 西方人名的第一个字 | 【姓氏】 | deepen | 【赛尼】 | 【24300】 | [Delhi] |
| --- | --- | --- | --- | --- | --- |

**Approach-1 :**
在下面的例子中，我们将使用聚结函数合并行。

**查询连接 SQL Server 中的行–**

```sql
DECLARE @Names VARCHAR(MAX)  
SELECT @Names = COALESCE(@Names + ', ', '') + [FirstName] 
FROM [geek_demo]
SELECT @Names AS [List of All Names]
```

**输出:**

<figure class="table">

| List of all names |
| --- |
| Ankit, Barbita, Chetan, Dipka, Isa, Guxi, Mega, Parur. |

</figure>

**Approach-2 :**
在下面的例子中，我们也将组合姓氏行。

**查询连接 SQL Server 中的行–**

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

**输出:**

<figure class="table">

| List of all names | List of all surnames |
| --- | --- |
| Ankit, Barbita, Chetan, Dipka, Isa, Guxi, Mega, Parur. | Puta, Duta, Jain, Saini, Sharma, Singer, Gauillard, Living Goddess. |

</figure>

**方法-3 :**
在下面的例子中，我们也将连接姓氏行。

**查询连接 SQL Server 中的行–**

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

**输出:**

<figure class="table">

| Name list of all names | First name list of all surnames |
| --- | --- |
| Ankit, Barbita, Chetan, Dipka, Isa, Guxi, Mega, Parur. | Puta, Duta, Jain, Saini, Sharma, Singer, Gauillard, Living Goddess. |

</figure>

**Approach-4 :**
在下面的例子中，我们将使用 stuff 函数结合两列(名字&姓氏)的行，并用于 XML 路径。

**查询连接 SQL Server 中的行–**

```sql
SELECT STUFF((
   SELECT ',' + SPACE(1) + [FirstName],
   ' ' + SPACE(1) + [LastName]
 FROM [geek_demo]
  FOR XML PATH(''), TYPE).value('.', 'VARCHAR(MAX)'), 1, 1, '')
AS [List Of All Names]
```

**输出:**

<figure class="table">

| name list |
| --- |
| Ankit Gupta, Babita Duta, Chetan Jain, Dipka Seni, Isha Sharma, Guxi Singh, Mega Gauillard, Parul Living Goddess. |

</figure>

**示例-2 :**
让我们假设我们下面有一个名为**“geek _ demo 1”**–

<figure class="table">安基特T26T58T63】khushi@gfg.orgT66T69】2017 年 3 月 03 日

| Table name of | Date of joining | e-mail |
| --- | --- | --- |
| May 04 th, 2018 | ankit@gfg.org |
| Babita | deepak@gfg.org |
| Isa | May 24(th), 2018 | 伊莎@gfg.org |
| Kehu | July 17(th), 2018 | Mika |  |

</figure>

**方法-1 :**
在下面的例子中，我们将使用 SQL Server 中的 CONCAT 函数将行组合成一个字符串。

**查询连接 SQL Server 中的行–**

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

**输出:**

<figure class="table">

| List of all names | All e-mail lists |
| --- | --- |
| Ankit, Babita, Chetan, Dipka, Isha, Guxi, Mega, Parur. | ankit@gfg.org、babita@gfg.org、chetan@gfg.org、deepak@gfg.org、isha@gfg.org、khushi@gfg.org、megha@gfg.org、parul@gfg.org |

</figure>

**方法-2 :**
在下面的示例中，我们将使用 SPACE 和 for XML 路径组合 SQL Server 中的行。

**查询连接 SQL Server 中的行–**

```sql
SELECT STUFF((
  SELECT ',' + SPACE(1) + [Email]
  FROM [geek_demo]
  FOR XML PATH(''), TYPE).value('.', 'VARCHAR(MAX)'), 1, 1, '')
AS [List Of All Emails]
```

**输出:**

<figure class="table">

| All mailing lists |
| --- |
| ankit@gfg.org、babita@gfg.org、chetan@gfg.org、deepak@gfg.org、isha@gfg.org、khushi@gfg.org、megha@gfg.org、parul@gfg.org |

</figure>