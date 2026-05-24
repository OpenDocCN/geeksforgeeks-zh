# 如何在 Java 中设置双精度值的精度？

> 原文: [https://www.geeksforgeeks.org/how-to-set-precision-for-double-values-in-java/](https://www.geeksforgeeks.org/how-to-set-precision-for-double-values-in-java/)

给定一个双精度值 `val`，任务是将其精度值设置为特定的小数位。

**例:**

```java
Input: val = 1 
Output: 1.0000
Upto 4 decimal places

Input : 12.5
Output : 12.500000
Upto 6 decimal places
```

## 方法：使用 `String.format()`

我们可以使用 [`String.format()`](https://www.geeksforgeeks.org/java-string-format-examples/) 方法将十进制数格式化为某种特定的格式。

**语法:**

```java
String.format("%.Df", decimalValue);

where D is the number required number of Decimal places.
```

下面是上述方法的实现：

### Java 实现

```java
import java.io.*;
import java.lang.*;

class GFG {
  public static void main(String[] args) {

    double a = 0.9;

    // Setting the precision to 20 places
    System.out.println(
      String.format("%.20f", a));

    double b = 1;

    // Setting the precision to 5 places
    System.out.println(
      String.format("%.5f", b));
  }
}
```

**输出**

```java
0.90000000000000000000
1.00000
```