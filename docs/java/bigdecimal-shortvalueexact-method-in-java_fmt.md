# Java中的BigDecimal shortValueExact()方法

> 原文：[https://www.geeksforgeeks.org/bigdecimal-shortvalueexact-method-in-java/](https://www.geeksforgeeks.org/bigdecimal-shortvalueexact-method-in-java/)

`java.math.BigDecimal.shortValueExact()`是Java中的一个内置方法，它将这个`BigDecimal`转换成一个`short`类型，并检查信息是否丢失。如果这个`BigDecimal`有一个非零的小数部分，或者超出了`short`结果的可能范围，那么会抛出一个`ArithmeticException`。

## 语法
```java
public short shortValueExact()
```

## 参数
该方法不接受任何参数。

## 返回值
该方法返回`BigDecimal`对象的`short`值。

以下程序说明了上述方法：

## 程序1
```java
// Program to demonstrate shortValueExact() method of BigDecimal

import java.math.*;

public class gfg {

    public static void main(String[] args)
    {
        BigDecimal b1 = new BigDecimal("457");
        BigDecimal b2 = new BigDecimal("4785");

        // Assigning the short value of BigDecimal objects b1 and b2
        // to short s1, s2 respectively
        short s1 = b1.shortValueExact();
        short s2 = b2.shortValueExact();

        // Printing s1, s2 values
        System.out.println("Exact short value of " + b1 + " is " + s1);
        System.out.println("Exact short value of " + b2 + " is " + s2);
    }
}
```

**Output:**
```java
Exact short value of 457 is 457
Exact short value of 4785 is 4785
```

## 程序2
```java
// Program to demonstrate shortValueExact() method of BigDecimal

import java.math.*;

public class gfg {

    public static void main(String[] args)
    {
        BigDecimal b1 = new BigDecimal("127");
        BigDecimal b2 = new BigDecimal("1455");

        // assign the short value of BigDecimal objects b1 and b2
        // to short s1, s2 respectively
        short s1 = b1.shortValueExact();
        short s2 = b2.shortValueExact();

        // print s1, s2 values
        System.out.println("Exact short value of " + b1 + " is " + s1);
        System.out.println("Exact short value of " + b2 + " is " + s2);
    }
}
```

**Output:**
```java
Exact short value of 127 is 127
Exact short value of 1455 is 1455
```

## 参考
[https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#shortValueExact()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#shortValueExact())