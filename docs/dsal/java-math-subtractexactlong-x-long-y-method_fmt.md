# Java Math.subtractExact(long x, long y) 方法

> 原文：[https://www.geeksforgeeks.org/java-math-subtractexactlong-x-long-y-method/](https://www.geeksforgeeks.org/java-math-subtractexactlong-x-long-y-method/)

`java.lang.Math.subtractExact()` 是 Java 中的一个内置数学函数，它返回参数的差值。如果结果溢出 `long` 类型范围，它将引发异常。由于 `subtractExact(long x, long y)` 是 `static` 方法，所以不需要创建对象。

## 语法

```java
public static long subtractExact(long x, long y)
```

**参数：**
*   `x`：第一个值。
*   `y`：要从第一个值中减去的第二个值。

**返回值：**
此方法返回参数的差值。

**异常：**
它抛出 `ArithmeticException` - 如果结果溢出 `long` 类型范围。

## 示例

以下示例展示了 `java.lang.Math.subtractExact()` 方法的工作方式。

```java
// Java program to demonstrate working
// of java.lang.Math.subtractExact() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        long x = 11111111111l;
        long y = 999l;

        System.out.println(Math.subtractExact(x, y));
    }
}
```

**输出：**

```
11111110112
```

```java
// Java program to demonstrate working
// of java.lang.Math.subtractExact() method
import java.lang.Math;

class Gfg2 {

    // driver code
    public static void main(String args[])
    {
        long a = Long.MIN_VALUE;
        long b = 1;

        System.out.println(Math.subtractExact(a, b));
    }
}
```

**输出：**

```
Runtime Error :
Exception in thread "main" java.lang.ArithmeticException: long overflow
    at java.lang.Math.subtractExact(Math.java:849)
    at Gfg2.main(File.java:13)
```