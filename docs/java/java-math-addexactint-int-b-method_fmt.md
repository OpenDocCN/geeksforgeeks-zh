# Java Math addExact(int a, int b)方法

> 原文: [https://www.geeksforgeeks.org/java-math-addexactint-int-b-method/](https://www.geeksforgeeks.org/java-math-addexactint-int-b-method/)

`java.lang.Math.addExact()`是 Java 中的一个内置数学函数，它返回其参数的总和。如果结果溢出一个 `int`，它会抛出一个异常。由于 `addExact(int a, int b)` 是 `static` 的，所以不需要创建对象。

## 语法:

```java
public static int addExact(int a, int b)
```

**参数：**
- `a` : 第一个值
- `b` : 第二个值

**返回：**
此方法返回其参数的和。

**异常：**
它抛出 `ArithmeticException` - 如果结果溢出一个 `int`。

## 示例:

展示 `java.lang.Math.addExact()` 方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.addExact() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        int a = 100;
        int b = 200;

        System.out.println(Math.addExact(a, b));
    }
}
```

**输出：**

```java
300
```

```java
// Java program to demonstrate working
// of java.lang.Math.addExact() method
import java.lang.Math;

class Gfg2 {

    // driver code
    public static void main(String args[])
    {
        int x = Integer.MAX_VALUE;
        int y = 200;

        System.out.println(Math.addExact(x, y));
    }
}
```

**输出：**

```java
Runtime Error :
Exception in thread "main" java.lang.ArithmeticException: integer overflow
    at java.lang.Math.addExact(Math.java:790)
    at Gfg2.main(File.java:13)
```