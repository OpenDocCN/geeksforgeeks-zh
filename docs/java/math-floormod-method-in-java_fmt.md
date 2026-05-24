# Java 中的 Math floorMod() 方法

> 原文: [https://www.geeksforgeeks.org/math-floormod-method-in-java/](https://www.geeksforgeeks.org/math-floormod-method-in-java/)

`java.lang.Math.floorMod()` 是 Java 中的内置数学函数，它返回传递给它的整数参数的地板模数。因此，地板模数为 `(a – (floorDiv(a, b) * b))`，与除数 `b` 符号相同，在 `-abs(b) < t < +abs(b)` 范围内。

`floorDiv` 和 `floorMod` 之间的关系是:
`floorDiv(a, b) * b + floorMod(a, b) == a`

`floorMod` 和 `%` 运算符之间的值差异是由于返回小于或等于商的整数的 `floorDiv` 和返回最接近零的整数的 `/` 运算符之间的差异。

## 语法

```java
public static int floorMod(int a, int b)
public static int floorMod(long a, long b)
```

## 参数

函数接受两个参数。

*   `a`：这是指被除数（分红）值。
*   `b`：这是指除数（divisor）值。

参数可以是数据类型 `int` 或 `long`。

## 异常

如果除数为零，则抛出 `ArithmeticException`。

## 返回值

该方法返回地板模数 `x – (floorDiv(x, y) * y)`。

## 示例程序

下面的程序用来说明 `java.lang.Math.floorMod()` 方法的工作原理。

### 程序 1

```java
// Java program to demonstrate working
// of java.lang.Math.floorMod() method
import java.lang.Math;

class Gfg1 {

    public static void main(String args[])
    {
        int a = 25, b = 5;
        System.out.println(Math.floorMod(a, b));

        // Divisor and dividend is having same sign
        int c = 123, d = 50;
        System.out.println(Math.floorMod(c, d));

        // Divisor is having negative sign
        int e = 123, f = -50;
        System.out.println(Math.floorMod(e, f));

        // Dividend is having negative sign
        int g = -123, h = 50;
        System.out.println(Math.floorMod(g, h));
    }
}
```

**输出:**

```java
0
23
-27
27
```

### 程序 2

```java
// Java program to demonstrate working
// of java.lang.Math.floorMod() method
import java.lang.Math;

class Gfg2 {

    public static void main(String args[])
    {
        int x = 200;
        int y = 0;

        System.out.println(Math.floorMod(x, y));
    }
}
```

**输出:**

```java
Runtime Error :
Exception in thread "main" java.lang.ArithmeticException: / by zero
    at java.lang.Math.floorDiv(Math.java:1052)
    at java.lang.Math.floorMod(Math.java:1139)
    at Gfg2.main(File.java:13)
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/lang/Math.html#floorMod-int-int-](https://docs.oracle.com/javase/8/docs/api/java/lang/Math.html#floorMod-int-int-)