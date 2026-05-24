# SQL |非运算符

> 原文:[https://www.geeksforgeeks.org/sql-not-operator/](https://www.geeksforgeeks.org/sql-not-operator/)

**NOT 语法**
选择第 1 列、第 2 列、…FROM _ table _ name WHERE NOT 条件；
**演示数据库**
以下是从北风样本数据库的“客户”表中选择的:

| 客户编号 | 用户姓名 | 城市 | 邮政编码 | 国家 |
| one | 疾速追杀 | 纽约 | One thousand two hundred and forty-eight | 美利坚合众国 |
| Two | 在号角周围 | 伦敦 | WA1 1DP | 英国 |
| three | 罗汉 | 新德里 | One hundred thousand and eighty-four | 印度 |

**NOT 示例**
以下 SQL 语句从国家不是“英国”的“客户”中选择所有字段
从不是国家=英国的客户中选择*字段；

| 客户编号 | 用户姓名 | 城市 | 邮政编码 | 国家 |
| one | 疾速追杀 | 纽约 | One thousand two hundred and forty-eight | 美利坚合众国 |
| three | 罗汉 | 新德里 | One hundred thousand and eighty-four | 印度 |

**组合 and、OR 和 NOT**
您也可以组合 AND、OR 和 NOT 运算符。
例:
1。)从非国家=美国且非国家=英国的客户中选择*；

| 客户编号 | 用户姓名 | 城市 | 邮政编码 | 国家 |
| three | 罗汉 | 新德里 | One hundred thousand and eighty-four | 印度 |