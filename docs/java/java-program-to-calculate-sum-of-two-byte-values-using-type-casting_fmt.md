# 使用类型转换计算两个字节值之和的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-calculate-sum-of-two-byte-values-using-type-casting/](https://www.geeksforgeeks.org/java-program-to-calculate-sum-of-two-byte-values-using-type-casting/)

Java 中两字节值的加法与普通整数加法相同。`byte`数据类型是 8 位带符号二进制补码整数。它的最小值为 -128，最大值为 127（含）。两字节值的和可能超过给定的字节限制，这种情况可以通过将两字节数的和存储在一个`int`变量中来处理。

## 示例

```java
Input:  firstByte = 10, secondByte = 23
Output: Sum = 33

Input:  firstByte = 10, secondByte = 23
Output: Sum = 33
```

## 类型转换

类型转换就是将一种数据类型转换成另一种数据类型。例如，在这个程序中，字节值被转换成一个整数。

## 方法

1.  声明并初始化两个`byte`类型的变量。
2.  声明一个`int`类型的变量。
3.  将两个`byte`的和存储在`int`变量中。

下面是上述方法的实现。

```java
// Java Program to Calculate Sum of
// Two Byte Values Using Type Casting

public class GFG {
    public static void main(String[] args)
    {
        // create two variable of byte type
        byte firstByte = 113;
        byte secondByte = 123;

        // create int variable to store result
        int sum;

        sum = firstByte + secondByte;
        System.out.println("sum = " + sum);
    }
}
```

**输出**

```
sum = 236
```