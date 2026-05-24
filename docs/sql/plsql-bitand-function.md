# PLSQL | BITAND 函数

> 原文:[https://www.geeksforgeeks.org/plsql-bitand-function/](https://www.geeksforgeeks.org/plsql-bitand-function/)

**BITAND** 是 PLSQL 中内置的[函数，用于返回一个整数值，该整数值通过对两个给定的输入十进制数进行“与”运算来计算。在内部，这些输入的十进制数被转换成二进制数，然后执行“与”运算，结果作为输出返回。](https://www.geeksforgeeks.org/functions-in-plsql/)

**语法:**

```sql
BITAND(num1, num2)
```

**参数使用:**
该功能接受两个参数，分别为 **num1** 和 **num2** 。这两个参数是输入的十进制数，内部转换成二进制数，调用 BITAND 函数。

**返回值:**
该函数返回一个整数值，该整数值是通过对两个给定的输入十进制数进行逐位“与”运算来计算的。

**支持的 Oracle/PLSQL 版本如下:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

让我们看一些例子来说明 BITAND 函数:

**示例-1:**

```sql
DECLARE 
   Test_Number number1 := 5;
   Test_Number number2 := 3;

BEGIN 
   dbms_output.put_line(BITAND(Test_Number number1, 
                               Test_Number number2)); 

END;  
```

**输出:**

```sql
1
```

这里取两个数字 5 和 3 作为参数。这两个十进制数被转换成等价的二进制数。5 和 3 的二进制等价分别是 101 和 011。稍后，这两个二进制数进行“与”运算，得到一个新的二进制数 001，它的十进制等价物是 1，因此 1 作为输出返回。

**示例-2:**

```sql
DECLARE 
   Test_Number number1 := 5;
   Test_Number number2 := 0;

BEGIN 
   dbms_output.put_line(BITAND(Test_Number number1, 
                               Test_Number number2)); 

END;  
```

**输出:**

```sql
0
```

这里取两个数字 5 和 0 作为参数。这两个十进制数被转换成等价的二进制数。5 和 0 的二进制等价物分别是 101 和 000。稍后，这两个二进制数进行“与”运算，得到一个新的二进制数 000，它的十进制等价物是 0，因此 0 作为输出返回。

**优势:**
该函数用于计算两个给定输入十进制数的位与运算。