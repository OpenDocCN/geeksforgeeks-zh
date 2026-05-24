# Java 中的 `Integer.numberOfLeadingZeros()` 方法示例

> 原文：[https://www.geeksforgeeks.org/integer-numberofleadingzeros-method-in-java-with-example/](https://www.geeksforgeeks.org/integer-numberofleadingzeros-method-in-java-with-example/)

`java.lang.Integer.numberOfLeadingZeros()` 是一个返回指定整数值的二进制补码表示中最高阶（即最左边或最高有效的“1”位）一位之前的零（0）位总数的方法。或者我们可以说，它是将 `int` 值转换为二进制，然后考虑最高一位并返回其之前的零位数的函数。如果指定的整数值在其二进制补码表示中没有一位，换句话说，如果它等于零，那么它将返回 32。

## 语法

```java
public static int numberOfLeadingZeros(int arg)
```

## 参数

该方法接受单个参数 `arg`，为整数值。

## 返回值

该方法返回指定 `int` 值的二进制补码二进制表示中最高阶 set 位之前的零位数，如果该值等于零，则返回 32。

## 说明

*   考虑任意整数 `arg = 19`
*   二进制表示 = `0001 0011`
*   最高位(5)，即 `0001 0000`
*   所以结果 = `16 - 5`，即 `11`

下面的程序说明了 `java.lang.Integer.numberOfLeadingZeros()` 方法。

## 示例程序

### 程序 1：为正数

```java
// Java program to illustrate the
// java.lang.Integer.numberOfLeadingZeros()
import java.lang.*;

public class LeadingZeros {

    public static void main(String[] args)
    {

        int a = 155;
        System.out.println("Integral Number = " + a);

        // Returns the number of zero bits preceding the highest-order
        // leftmost one-bit
        System.out.print("Number of Leading Zeros = ");
        System.out.println(Integer.numberOfLeadingZeros(a));
        a = 10;
        System.out.println("Integral Number = " + a);

        // Returns the number of zero bits preceding the highest-order
        // leftmost one-bit
        System.out.print("Number of Leading Zeros = ");
        System.out.println(Integer.numberOfLeadingZeros(a));
    }
}
```

**输出：**

```java
Integral Number = 155
Number of Leading Zeros = 24
Integral Number = 10
Number of Leading Zeros = 28
```