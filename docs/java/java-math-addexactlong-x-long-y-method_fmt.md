# Java Math addExact(long x, long y) 方法

> 原文: [https://www.geeksforgeeks.org/java-math-addexactlong-x-long-y-method/](https://www.geeksforgeeks.org/java-math-addexactlong-x-long-y-method/)

`java.lang.Math.addExact()` 是 Java 中的一个内置数学函数，它返回其参数的总和。如果结果溢出一个长整型数，它会抛出一个异常。由于 `addExact(long x, long y)` 为 `static`，因此不需要创建对象。

## 语法

```java
public static long addExact(long x, long y)
```

**参数：**
- `x`：第一个值
- `y`：第二个值

**返回值：**
此方法返回其参数的和。

**异常：**
它抛出 `ArithmeticException` - 如果结果溢出一个 `long`。

## 示例

展示 `java.lang.Math.addExact()` 方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.addExact() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        long x = 9999999999l;
        long y = 1l;

        System.out.println(Math.addExact(x, y));
    }
}
```

**输出：**

```
10000000000
```

```java
// Java program to demonstrate working
// of java.lang.Math.addExact() method
import java.lang.Math;

class Gfg2 {

    // driver code
    public static void main(String args[])
    {
        long a = Long.MAX_VALUE;
        long b = 2l;

        System.out.println(Math.addExact(a, b));
    }
}
```

**输出：**

```
Runtime Error :
Exception in thread "main" java.lang.ArithmeticException: long overflow
    at java.lang.Math.addExact(Math.java:809)
    at Gfg2.main(File.java:13)
```