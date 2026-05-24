# Java 中的 BigDecimal min()方法

> 原文：`https://www.geeksforgeeks.org/bigdecimal-min-method-in-java/`

Java 中的 `BigDecimal.min(BigDecimal val)` 方法用于比较两个 `BigDecimal` 值，并返回这两个值的最小值。

## 语法

```java
public BigDecimal min(BigDecimal val)
```

## 参数

函数接受一个 `BigDecimal` 对象 `val` 作为参数，其值与该 `BigDecimal` 对象的值进行比较，并返回最小值。

## 返回值

该方法返回 `BigDecimal` 数，其值是 `this` `BigDecimal` 数和 `val` 中较小的一个。如果两者相等，则返回 `this` `BigDecimal`。

## 例

```java
Input :  a = 17.000041900, b = 17.0000418999
Output : 17.0000418999

Input : a = 235900000146, b = 236000000000
Output : 235900000146
```

下面的程序将说明 `BigDecimal` 类的 `min()` 函数：

### 程序 1

```java
/*Java program to illustrate
use of BigDecimal min() 
function in Java      */
import java.math.*;

public class GFG {

public static void main(String[] args)
    {

// Creating 2 BigDecimal objects
        BigDecimal a, b;

a = new BigDecimal("17.000041900");
        b = new BigDecimal("17.0000418999");

// print the maximum value
        System.out.println("Minimum Value among " + a + 
                        " and " + b + " is " + a.min(b));
    }
}
```

### 输出

```java
Minimum Value among 17.000041900 and 17.0000418999 is 17.0000418999
```

### 程序二

```java
/*Java program to illustrate
use of BigDecimal min() 
to display minimum length
among two strings  */
import java.math.*;

public class GFG {

public static void main(String[] args)
    {

// Create 2 BigDecimal objects
        BigDecimal a, b;
        String s = "GeeksforGeeks";
        String str = "GeeksClasses";

int l1, l2;
        l1 = s.length();
        l2 = str.length();

a = new BigDecimal(l1);
        b = new BigDecimal(l2);

// Print the respective lengths
        System.out.println("Length of string " + s + " is " + a);
        System.out.println("Length of string " + str + " is " + b);
        // Print the maximum value
        System.out.println("Minimum length is " + a.min(b));
    }
}
```

### 输出

```java
Length of string GeeksforGeeks is 13
Length of string GeeksClasses is 12
Minimum length is 12
```

## 参考

`https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#min()`