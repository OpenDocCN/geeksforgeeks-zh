# 使用 SQL 操作 R 数据帧

> 原文:[https://www . geesforgeks . org/operate-r-data-frames-use-SQL/](https://www.geeksforgeeks.org/manipulate-r-data-frames-using-sql/)

使用 [SQL](https://www.geeksforgeeks.org/structured-query-language/) 在 [R 编程](https://www.geeksforgeeks.org/introduction-to-r-programming-language/)中操作[数据框](https://www.geeksforgeeks.org/r-data-frames/)可以使用 [**sqldf**](https://www.rdocumentation.org/packages/sqldf/versions/0.4-11) 包轻松完成。R 中的这个包提供了一种允许用 SQL 进行数据框操作的机制，还有助于连接有限数量的数据库。R 中的 sqldf 包基本上是用来执行数据帧上的 SQL 命令或语句的。可以简单地用数据框名而不是 R 中的表名来指定 SQL 语句，然后会发生以下情况:

*   创建一个具有适当模式或表布局的数据库
*   数据框会自动加载到创建的数据库中
*   执行特定的 SQL 语句或命令
*   结果被检索回 R，并且
*   数据库被自动删除。

这使得数据库的存在相当透明。这种方法可以导致更快的 R 计算。使用一些试探法获得结果，以便确定要分配给结果数据帧的每一列的类。

Working With sqldf in R

使用 sqldf 包可以在 R 中执行一些 SQL 操作。让我们使用来自高速公路数据的两个 csv 文件。

*   [碰撞. csv](https://drive.google.com/file/d/0B_5j9YRiO1GsUlRsMXgwVDdWSFE/view) 包含年份、道路、N _ 碰撞和体积。
*   [包含道路、区域和长度的道路. csv](https://drive.google.com/file/d/0B_5j9YRiO1GsWXFZOGVqSnVIYlU/view) 。

为了使用 sqldf 包，首先按如下方式安装它:

```sql
install.packages("sqldf")
```

正确安装后，将包包含在 R 脚本中，如下所示:

```sql
library(sqldf)
```

现在将数据加载到脚本中。为此，请使用 **setwd()** 功能将当前目录更改为包含 csv 文件 crashes.csv 和 roads.csv 的目录。
**例:**

## r

```sql
# Importing required library
library(sqldf)

# Changing the directory
setwd("C:\\Users\\SHAONI\\Documents\\
                     R\\win-library")

# Reading the csv files
crashes <- read.csv("crashes.csv")
roads <- read.csv("roads.csv")

# Displaying the data in crashes.csv
head(crashes)
tail(crashes)

# Displaying the data in roads.csv
print(roads)
```

**输出:**

```sql
  Year     Road       N_Crashes Volume
1 1991 Interstate 65        25  40000
2 1992 Interstate 65        37  41000
3 1993 Interstate 65        45  45000
4 1994 Interstate 65        46  45600
5 1995 Interstate 65        46  49000
6 1996 Interstate 65        59  51000

    Year  Road           N_Crashes Volume
105 2007 Interstate 275        32  21900
106 2008 Interstate 275        21  21850
107 2009 Interstate 275        25  22100
108 2010 Interstate 275        24  21500
109 2011 Interstate 275        23  20300
110 2012 Interstate 275        22  21200

           Road       District   Length
1 Interstate 65     Greenfield    262
2 Interstate 70      Vincennes    156
3         US-36 Crawfordsville    139
4         US-40     Greenfield    150
5         US-52 Crawfordsville    172
```

现在使用 sqldf 包的 **sqldf()** 函数对这些数据执行任何 SQL 操作。

#### 连接和合并数据帧

最常见的 SQL 操作是**连接操作**。可以使用 **sqldf()** 执行左连接和内连接。目前， **sqldf()** 不支持完全外连接和右连接操作。除了 sqldf 包，我们还需要包括 [**tcltk**](https://www.rdocumentation.org/packages/tcltk/versions/3.6.2) 包。
**示例 1:执行左连接操作**

## r

```sql
# Perform Left Join

# Importing required library
library(sqldf)
library(tcltk)

# Setting the directory
setwd("C:\\Users\\SHAONI\\Documents\\
                     R\\win-library")

# Reading the csv files
crashes <- read.csv("crashes.csv")
roads <- read.csv("roads.csv")

# Performing left join
join_string <- "select crashes.*,
                 roads.District,
                 roads.Length
                 from crashes
                 left join
                 roads on
                 crashes.Road = roads.Road"

# Resultant data frame
crashes_join_roads <- sqldf(join_string,
                stringsAsFactors = FALSE)
head(crashes_join_roads)
tail(crashes_join_roads)
```

**输出:**

```sql
  Year    Road        N_Crashes Volume  District   Length
1 1991 Interstate 65        25  40000 Greenfield    262
2 1992 Interstate 65        37  41000 Greenfield    262
3 1993 Interstate 65        45  45000 Greenfield    262
4 1994 Interstate 65        46  45600 Greenfield    262
5 1995 Interstate 65        46  49000 Greenfield    262
6 1996 Interstate 65        59  51000 Greenfield    262

    Year  Road          N_Crashes Volume     District     Length
105 2007 Interstate 275        32  21900     <NA>     NA
106 2008 Interstate 275        21  21850     <NA>     NA
107 2009 Interstate 275        25  22100     <NA>     NA
108 2010 Interstate 275        24  21500     <NA>     NA
109 2011 Interstate 275        23  20300     <NA>     NA
110 2012 Interstate 275        22  21200     <NA>     NA
```

**解释:**
crasses _ join _ roads 是一个由 sqldf 语句创建的新数据帧，它存储了 join 操作的结果。sqldf()函数或操作至少需要一个字符串和一个 SQL 操作。stringsAsFactors 参数用于将字符类分配给分类数据，而不是因子类。
**示例 2:执行内部连接**

## r

```sql
# Perform Inner Join

# Importing required package
library(sqldf)
library(tcltk)

# Selecting the proper directory
setwd("C:\\Users\\SHAONI\\Documents\\
                     R\\win-library")
# Reading the csv files
crashes <- read.csv("crashes.csv")
roads <- read.csv("roads.csv")

# Performing the inner join
join_string2 <- "select crashes.*,
                 roads.District,
                 roads.Length
                 from crashes
                 inner join
                 roads on
                 crashes.Road = roads.Road"

# The new data frame
crashes_join_roads2 <- sqldf(join_string2,
                 stringsAsFactors = FALSE)
head(crashes_join_roads2)
tail(crashes_join_roads2)
```

**输出:**

```sql

  Year     Road       N_Crashes Volume  District  Length
1 1991 Interstate 65        25  40000 Greenfield    262
2 1992 Interstate 65        37  41000 Greenfield    262
3 1993 Interstate 65        45  45000 Greenfield    262
4 1994 Interstate 65        46  45600 Greenfield    262
5 1995 Interstate 65        46  49000 Greenfield    262
6 1996 Interstate 65        59  51000 Greenfield    262

   Year  Road  N_Crashes Volume   District      Length
83 2007 US-36        49  24000 Crawfordsville    139
84 2008 US-36        52  24500 Crawfordsville    139
85 2009 US-36        55  24700 Crawfordsville    139
86 2010 US-36        35  23000 Crawfordsville    139
87 2011 US-36        33  21000 Crawfordsville    139
88 2012 US-36        31  20500 Crawfordsville    139
```

这里只有匹配的行保留在结果数据帧中。
现在我们来看看 **merge()** 函数是如何工作的。在 R 中，与 sqldf()函数不同，合并操作能够执行左连接、右连接、内连接和完全外连接。此外，可以使用 merge()操作轻松执行类似 sqldf()的等效操作。
**例 3:**

## r

```sql
# Perform Merge operation

# Import required library
library(sqldf)
library(tcltk)

setwd("C:\\Users\\SHAONI\\Documents\\
                     R\\win-library")

# Reading the two csv files
crashes <- read.csv("crashes.csv")
roads <- read.csv("roads.csv")
# Merge the two data frames
crashes_merge_roads2 <- merge(crashes,
                              roads,
                              by = c("Road"),
                              all.x = TRUE)
head(crashes_merge_roads2)
tail(crashes_merge_roads2)
```

**输出:**

```sql

     Road        Year  N_Crashes Volume    District    Length
1 Interstate 275 1994        21  21200     <NA>     NA
2 Interstate 275 1995        28  23200     <NA>     NA
3 Interstate 275 1996        22  20000     <NA>     NA
4 Interstate 275 1997        27  18000     <NA>     NA
5 Interstate 275 1998        21  19500     <NA>     NA
6 Interstate 275 1999        22  21000     <NA>     NA

     Road Year N_Crashes Volume   District  Length
105 US-40 2003        94  55200 Greenfield    150
106 US-40 2004        25  55300 Greenfield    150
107 US-40 2009        67  65000 Greenfield    150
108 US-40 2010       102  67000 Greenfield    150
109 US-40 2011        87  67500 Greenfield    150
110 US-40 2012        32  67500 Greenfield    150
```

当我们使用 merge()函数时，我们将看到结果数据帧中的行被重新排列。

#### 使用 where 子句

r 可以执行与 SQL 完全相同的操作。因此，要使用包含任何条件的 SQL 语句，请使用 **where 子句**。
**示例:**
让我们看看如何通过在查询中包含 where 子句，使用合并和子集操作的组合来执行内部连接。

## r

```sql
# Using where clause

# Importing required library
library(sqldf)
library(plyr)
library(tcltk)

setwd("C:\\Users\\SHAONI\\Documents\\
                     R\\win-library")
crashes <- read.csv("crashes.csv")
roads <- read.csv("roads.csv")

# Using the where clause
join_string2 <- "select crashes.*,
                 roads.District,
                 roads.Length
                 from crashes
                 inner join
                 roads on
                 crashes.Road = roads.Road
                 where
                 crashes.Road = 'US-40'" 

crashes_join_roads4 <- sqldf(join_string2,
                 stringsAsFactors = FALSE)
head(crashes_join_roads4)
tail(crashes_join_roads4)
```

**输出:**

```sql
  Year  Road  N_Crashes Volume District   Length
1 1991 US-40        46  21000 Greenfield    150
2 1992 US-40       101  21500 Greenfield    150
3 1993 US-40        76  23000 Greenfield    150
4 1994 US-40        72  21000 Greenfield    150
5 1995 US-40        75  24000 Greenfield    150
6 1996 US-40       136  23500 Greenfield    150

   Year  Road N_Crashes  Volume  District  Length
17 2007 US-40        45  59500 Greenfield    150
18 2008 US-40        23  61000 Greenfield    150
19 2009 US-40        67  65000 Greenfield    150
20 2010 US-40       102  67000 Greenfield    150
21 2011 US-40        87  67500 Greenfield    150
22 2012 US-40        32  67500 Greenfield    150
```

#### 聚合函数

在 sqldf 包中，聚合操作可以使用 **group by 子句**来执行。
**例:**

## r

```sql
# Perform aggregate operations

# Import required library
library(sqldf)
library(tcltk)

setwd("C:\\Users\\SHAONI\\Documents\\
                     R\\win-library")
crashes <- read.csv("crashes.csv")
roads <- read.csv("roads.csv")

# Group by clause
group_string <- "select crashes.Road,
                 avg(crashes.N_Crashes)
                 as Mean_Crashes
                 from crashes
                 left join
                 roads on
                 crashes.Road = roads.Road
                 group by 1"
sqldf(group_string)
```

**输出:**

```sql
      Road         Mean_Crashes
1 Interstate 275     24.95455
2  Interstate 65    107.81818
3  Interstate 70     65.18182
4          US-36     48.00000
5          US-40     68.68182
```

sqldf()函数可用于执行某些类型的数据操作。要克服这些限制，请使用 R 脚本中的 **plyr** 包。哈德利·韦翰的 **plyr 软件包**可用于执行高级计算和数据操作。让我们看看它是如何工作的。
**例:**

## r

```sql
# Importing required library
library(sqldf)
library(plyr)
library(tcltk)

setwd("C:\\Users\\SHAONI\\Documents\\
                     R\\win-library")
crashes <- read.csv("crashes.csv")
roads <- read.csv("roads.csv")

ddply(
crashes_merge_roads,
c("Road"),
function(X)
data.frame(
  Mean_Crashes = mean(X$N_Crashes),
  Q1_Crashes = quantile(X$N_Crashes, 0.25),
  Q3_Crashes = quantile(X$N_Crashes, 0.75),
  Median_Crashes = quantile(X$N_Crashes, 0.50))
)
```

**输出:**

```sql

     Road        Mean_Crashes   Q1_Crashes Q3_Crashes   Median_Crashes
1 Interstate 65    107.81818      63.25     140.25          108.5
2 Interstate 70     65.18182      52.00      75.50           66.5
3         US-36     48.00000      42.00      57.25           47.0
4         US-40     68.68182      45.25      90.75           70.0
```