# MariaDB中的QUARTER()和SEC_TO_TIME()

> 原文: [https://www.geeksforgeeks.org/quarter-and-sec_to_time-in-mariadb/](https://www.geeksforgeeks.org/quarter-and-sec_to_time-in-mariadb/)

## 1. QUARTER功能

在MariaDB中，`QUARTER()`函数返回日期值的季度部分。在这个函数中，第一个参数是日期/日期时间。该函数返回给定日期值的季度（从1到4的数字）。1-3月的日期将返回1，4-6月的日期将返回2，7-9月的日期将返回3，10-12月的日期将返回4。

### 语法

```sql
QUARTER( date_value )
```

### 函数返回值

```sql
1 year = 12/3 = 4 Quarter
Jan to Mar
Apr to Jun
Jul to Sep
Oct to Nov
```

### 参数

| parameter | Describe |
| --- | --- |
| date_value | 从中提取季度的日期或日期时间值。 |

### 返回

它将返回日期值的季度部分。

### 示例-1

```sql
SELECT QUARTER('2020-02-17');
```

### 输出

```sql

```

### 示例-2

```sql
SELECT QUARTER('2020-05-17 15:21:05');
```

### 输出

```sql

```

### 示例-3

`CURDATE()`函数将返回系统日期的当前季度。

```sql
SELECT QUARTER(CURDATE());
```

### 输出

```sql

```

## 2. SEC_TO_TIME功能

在MariaDB中，`SEC_TO_TIME()`函数用于将数字秒转换为时间值。在这个函数中，第一个参数是秒数。此函数返回的时间值范围从`'-838:59:59'`到`'838:59:59'`。该函数将结果格式化为`'时:分:秒'`。它的工作原理与`TIME_TO_SEC()`函数相反。

### 语法

```sql
SEC_TO_TIME( seconds )
```

### 函数返回值

```sql
Range : '-838:59:59' to '838:59:59'
```

### 参数

| parameter | Describe |
| --- | --- |
| seconds | 表示秒数的数字。该值可以是正数或负数。 |

### 返回

返回时间值。

### 示例-1

```sql
SELECT SEC_TO_TIME(5);
```

### 输出

```sql
'00:00:05'
```

### 示例-2

```sql
SELECT SEC_TO_TIME(18700);
```

### 输出

```sql
'05:11:40'
```

### 示例-3

```sql
SELECT SEC_TO_TIME(-999);
```

### 输出

```sql
'-00:16:39'
```