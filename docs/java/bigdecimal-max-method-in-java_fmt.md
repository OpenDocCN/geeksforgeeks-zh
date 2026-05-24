# Java 中的 BigDecimal max()方法

> 原文：[https://www.geeksforgeeks.org/bigdecimal-max-method-in-java/](https://www.geeksforgeeks.org/bigdecimal-max-method-in-java/)

Java 中的`java.math.BigDecimal.max(BigDecimal val)`方法用于比较两个`BigDecimal`值并返回两者的**最大值**。这与 Java 中的`BigDecimal` `min()`方法相反。

## 语法：

```java
public BigDecimal max(BigDecimal val)
```

## 参数：
函数接受一个`BigDecimal`对象`val`作为参数，其值与该`BigDecimal`对象的值进行比较，并返回最大值。

## 返回值：
该方法返回`BigDecimal`数，其值为`this` `BigDecimal`数和`val`中的较大值。如果两者相等，则返回`this` `BigDecimal`。

## 示例：

```java
Input :  a = 17.000041900, b = 17.0000418999
Output : 17.000041900

Input : a = 235900000146, b = 236000000000
Output : 236000000000
```

下面的程序将说明`BigDecimal`类的`max()`函数。

## 程序 1：

```java
// Java program to illustrate use of
// BigDecimal max() function in Java      
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // create 2 BigDecimal objects
        BigDecimal a, b;

        a = new BigDecimal("235900000146");
        b = new BigDecimal("236000000000");

        // print the maximum value
        System.out.println("Maximum Value among " + a +
                           " and " + b + " is " + a.max(b));
    }
}
```

## Output：

```java
Maximum Value among 235900000146 and 236000000000 is 236000000000
```

## 程序 2：

```java
// Java program to illustrate use of BigDecimal max()
// to display maximum length among two strings in Java  
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
        System.out.println("Maximum length is " + a.max(b));
    }
}
```

## Output：

```java
Length of string GeeksforGeeks is 13
Length of string GeeksClasses is 12
Maximum length is 13
```

## 参考：
[https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#max()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#max())