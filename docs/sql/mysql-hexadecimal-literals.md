# MySQL |十六进制文字

> 原文:[https://www.geeksforgeeks.org/mysql-hexadecimal-literals/](https://www.geeksforgeeks.org/mysql-hexadecimal-literals/)

**字面意思:**
可以定义为给变量或常量的值。

**示例:**

```sql
int f = 2 
```

这里 f 是变量，2 是数值。

**十六进制文字:**
这些是以 16 为基数的整数(在编号系统中)。

**示例:**

```sql
int y = X'12A' 
```

一个十六进制文字前面应该是 0x 或者 X，它的值是 12A，也就是相当于十进制数字系统中的 298。

**语法:**
十六进制文字值以下列形式书写:

```sql
X'val' 
x'val'
0xval  
```

**值**代表任何十六进制数，即范围(0，1，…)内的任何数字..d、E、F)。在 0xval 中，标记 0x 区分大小写，因此不能写成 0xval”。但是，以 X 或 0x 开头的数字的字母大小写不区分大小写。

**例子:**
这些都是有效的文字。

```sql
X'015'
X'01aF'
x'BC'
x'2d'
0x7e4
0x88bA

```

这些是无效的文字。

```sql
X'1s' // s is not in range (0, 1, ...A, .., F)
0X'1'  // OX is not a valid notation, 
       // correct notation is 0x 
```

**注意:**X'val '或 X ' val '形式的符号包含偶数个数字，否则将引发语法错误。

```sql
mysql>select X'3' 
```

**错误 1064:** 您的 SQL 语法中有一个错误；查看与您的 MySQL 服务器版本相对应的手册，了解在“X”3 附近使用的正确语法。

通过在字符串的开头填充零，可以避免错误。

```sql
mysql> select X'03' 
               ->♥ 
```

如果以 0xval 形式写入的值包含奇数个数字，则它被视为在值的开头包含额外的前导零。像，0x123 被视为 0x0123。

**默认表示:**
默认情况下，十六进制文字是一个二进制字符串，其中每对代表一个字符。

**示例:**

```sql
mysql>select 0x65;
             -> e
mysql>select 5461626c65;
         -> Table
mysql>select 0x465;
         -> ♦e 
```

这里，在最后一个文字 0x465 中，输出是“e ”,因为 65 代表字母“e ”, 4 代表”。

空的十六进制文字值(X ' ')是零长度二进制字符串。

```sql
mysql>select X'', length(X'')
       -> binary 0 
```

**对十六进制文字的操作–**

1.  **COLLATE operation:**
    The default, character set of hexadecimal literal can be changed by using an optional character set introducer and *COLLATE* clause to convert it into a string of particular character set and collation.

    **语法:**

    ```sql
    [_charset_name] literal [COLLATE collation_name]
    ```

    **示例:**

    ```sql
    mysql>select _utf8 X'4745454B'
         -> GEEK
    mysql>select _utf8 X'4745454B' COLLATE utf8_danish_ci;
         -> GEEK

    ```

2.  **BIT Operations;**

    ```sql
    mysql>select X'01' | X'02', hex(X'01' | X'02')
          -> 3 3
    mysql>select _binary X'01' | X'02', hex(_binary X'01' | X'02')
          -> ♥ 03 
    ```

    对于十六进制文字，位操作会产生一个 BIGINT 值。与上面的代码一样，在不使用 _binary 导入器的情况下，不显示包含零的最高有效位。因此，通过使用 _ binary introducer，我们可以在二进制上下文中显式地指定它们。

3.  **算术运算:**
    在数值上下文中，十六进制文字被视为 BIGINT (64 位整数)。对于数值上下文，我们可以使用像+、-、*、/、%这样的算术运算符；

    ```sql
    mysql>select 0x67+0
          -> 103
    mysql>select 0x45*2
          -> 138

    ```

4.  **HEX() / UNHEX() fun:**
    We can use in-built function **HEX()** to convert a string or number in hexadecimal string.

    ```sql
    mysql>select hex('e')
          -> 65
    mysql>select hex('table')
          -> 5461626C65

    ```

    同样的，**unhx()**函数用于将每对十六进制数字转换为对应的字符。

    ```sql
    mysql>select unhex('5645')
           ->VE   
    mysql>select unhex('qq')
           ->NULL      

    ```

    在最后一个查询中，我们取消了返回空值的非十六进制数字，即(' qq ')。