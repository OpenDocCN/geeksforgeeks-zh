# 隐式光标和显式光标的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-implicit-and-explicit-cursors/](https://www.geeksforgeeks.org/difference-between-implicit-and-explicit-cursors/)

像 ORACLE 这样的数据库有一个内存区域，在那里处理指令和提取的数据。光标是指向这个区域的指针。该存储区中包含的数据也被称为**活动集**。光标可以大致分为**隐式光标**和**显式光标**。

## 隐式光标和显式光标的区别

| 隐式游标 | 显式游标 |
| --- | --- |
| 执行 `SELECT` 语句时，会自动创建隐式游标。 | 显式游标需要由用户通过提供名称来显式定义。 |
| 它们能够一次获取一行。 | 显式游标可以获取多行。 |
| 它们更容易出现错误，如数据错误等。 | 它们不太容易出错（数据错误等）。 |
| 为用户提供较少的编程控制。 | 用户/程序员拥有全部控制权。 |
| 隐式游标效率较低。 | 与隐式游标相比，显式游标更有效。 |
| 隐式游标定义为：<br>```sql<br>BEGIN<br>SELECT attr_name from table_name<br>where CONDITION;<br>END<br>``` | 显式游标定义为：<br>```sql<br>DECLARE<br>CURSOR cur_name IS<br>SELECT attr_name from table_name<br>where CONDITION;<br>BEGIN<br>...<br>``` |
| 隐式游标需要匿名缓冲内存来存储。 | 显式游标使用用户定义的内存空间进行存储。 |
| 光标属性使用前缀 `SQL`。<br>隐式游标的结构：`SQL%attr_name`<br>少数隐式游标属性是：`SQL%FOUND`，`SQL%NOTFOUND`，`SQL%ROWCOUNT` | 显式游标的结构：`cur_name%attr_name`<br>少数显式游标属性是：`cur_name%FOUND`，`cur_name%NOTFOUND`，`cur_name%ROWCOUNT` |