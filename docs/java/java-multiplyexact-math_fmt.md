# Java 中的 Math.multiplyExact()

> 原文链接：https://www.geeksforgeeks.org/java-multiplyexact-math/

`java.lang.Math.multiplyExact()` 是一个内置的 Java 数学函数，它返回参数的乘积。如果结果溢出一个 `int`，它将引发异常。由于 `multiplyExact(int a, int b)` 是 `static` 方法，所以不需要创建对象。

## 语法

```java
public static int multiplyExact(int a, int b)
public static double multiplyExact(int a, double b)
```

**参数：**
- `a`：第一个值
- `b`：第二个值

**返回值：**
此方法返回参数的乘积。

**异常：**
它抛出 `ArithmeticException` - 如果结果溢出一个 `int`。

## 示例

展示 `java.lang.Math.multiplyExact()` 方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.multiplyExact() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        int a = 25, b = 5;
        System.out.println(Math.multiplyExact(a, b));

        long c = 100, d = 50;
        System.out.println(Math.multiplyExact(c, d));
    }
}
```

**输出：**

```java
125
5000
```

```java
// Java program to demonstrate working
// of java.lang.Math.multiplyExact() method
import java.lang.Math;

class Gfg2 {

    // driver code
    public static void main(String args[])
    {
        int x = Integer.MAX_VALUE;
        int y = 2;

        System.out.println(Math.multiplyExact(x, y));
    }
}
```

**输出：**

```java
Runtime Error :
Exception in thread "main" java.lang.ArithmeticException: integer overflow
    at java.lang.Math.multiplyExact(Math.java:867)
    at Gfg2.main(File.java:13)
```