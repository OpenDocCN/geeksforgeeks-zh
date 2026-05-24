# PLSQL |转储功能

> 原文:[https://www.geeksforgeeks.org/plsql-dump-function/](https://www.geeksforgeeks.org/plsql-dump-function/)

PLSQL DUMP 函数用于返回 varchar2 值，该值包含数据类型代码、字节长度和表达式的内部表示形式。
PLSQL DUMP 函数接受一个表达式作为参数，如果表达式值为 NULL，那么 DUMP 函数返回 NULL。

**语法:**

```sql
DUMP( expression [, return_format] [, start_position] [, length] )
```

**使用的参数:**

1.  **表达式–**
    用于指定要分析的表达式。
2.  **return _ format–**
    它是一个可选参数，决定返回值的格式。
3.  **起始位置–**
    是一个可选参数，用于指定要返回的内部表示中的起始位置。
4.  **长度–**
    这是一个可选参数，用于指定要返回的内部表示中的长度。

**return _ format 参数接受以下值:**

*   8:八分音符
*   10:十进制符号
*   16:十六进制表示法
*   17:单个字符
*   1008:带有字符集名称的八进制记数法
*   1010:带有字符集名称的十进制表示法
*   1016:字符集名称的十六进制表示法
*   1017:具有字符集名称的单个字符

**返回值:**
DUMP 函数返回一个 VARCHAR2 值，但是如果省略 return_format、start_position 和 length 参数，DUMP 函数将以十进制表示法返回整个内部表示。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:**

```sql
SELECT DUMP('Geeksforgeeks') FROM dual 
```

**输出:**

![](img/4ede5e354fc8bb41f66947c0b8c558d0.png)

**例-2:**

```sql
SELECT DUMP('Geeksforgeeks', 10) FROM dual 
```

**输出:**

![](img/ce95a4899ab8932689dac212a16e03c5.png)

**例-3:**

```sql
SELECT DUMP('Geeksforgeeks', 16) FROM dual 
```

**输出:**

![](img/245d3b51c9b2e5f81516ec3a2d3538bf.png)

**例-4:**

```sql
SELECT DUMP('Geeksforgeeks', 17) FROM dual 
```

**输出:**

![](img/ba33283072a31ee92ca8f3d2d7eab405.png)

**例-5:**

```sql
SELECT DUMP('Geeksforgeeks', 1008) FROM dual 
```

**输出:**

![](img/77eeab2a059a73378a9f92ee9ccd61c1.png)