# 以三角形形式打印乘法表的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-print-the-multiplication-table-in-a-triangle-form/](https://www.geeksforgeeks.org/java-program-to-print-the-multiplication-table-in-a-triangle-form/)

在这种形式中，表格是按行和列显示的，在每一行中，只有相同列号的条目被填充。

**示例：**

```java
Input : rows = 6
Output:
1 
2 4 
3 6 9 
4 8 12 16 
5 10 15 20 25 
6 12 18 24 30 36  
```

**方法：** 思路是使用嵌套循环。首先，显示列号。然后，使用到嵌套循环来填充行的条目。

1.  在函数 `owner()` 中，首先输入行数 `n`。
2.  循环 `(i = 0; i < row; i++)` 用于打印列号行。
3.  循环 `(i = 0; i < line; i++)` 用于打印 `n` 行条目。
4.  嵌套循环 `(j = 0; j <= i; j++)` 用于打印当前条目。

下面是上述方法的实现。

## Java

```java
// Java Program to Print the Multiplication
// Table in Triangular Form

import java.util.*;

public class MultiplicationTableTrianglePattern {

    // Function to print tables in triangular form
    public static void main(String args[]) {
        int rows, i, j;

        Scanner in = new Scanner(System.in);

        rows = 6;

        // Loop to print multiplication
        // table in triangular form
        for (i = 1; i <= rows; i++) {
            for (j = 1; j <= i; j++) {
                System.out.print(i * j + " ");
            }
            System.out.println();
        }
    }
}
```

### 输出

```java
1 
2 4 
3 6 9 
4 8 12 16 
5 10 15 20 25 
6 12 18 24 30 36
```

### 时间复杂度

时间复杂度：`O(n^2)`，其中 `n` 为行数。