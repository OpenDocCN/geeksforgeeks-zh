# Java Math.incrementExact(int x) 方法

> 原文: [https://www.geeksforgeeks.org/java-math-incrementexactint-x-method/](https://www.geeksforgeeks.org/java-math-incrementexactint-x-method/)

`java.lang.Math.incrementExact()` 是 Java 中的内置数学函数，返回递增 1 的参数。如果结果溢出一个 `int`，它将引发异常。由于 `incrementExact(int x)` 是**静态的**，所以不需要创建对象。

## 语法

```
public static int incrementExact(int x)
```

**参数：**
`x`：要递增的值。

**返回值：**
此方法返回递增一后的参数。

**异常：**
它抛出 `ArithmeticException` - 如果结果溢出一个 `int`。

## 示例

展示 `java.lang.Math.incrementExact()` 方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.incrementExact() method
import java.lang.Math;

class Gfg1 {

// driver code
    public static void main(String args[])
    {
        int a = 0;

        for (int i = 0; i < 5; i++) {
            a = Math.incrementExact(a);
            System.out.println(a);
        }
    }
}
```

**输出：**

```
1
2
3
4
5
```

```
// Java program to demonstrate working
// of java.lang.Math.incrementExact() method
import java.lang.Math;

class Gfg2 {

// driver code
    public static void main(String args[])
    {
        int x = Integer.MAX_VALUE;

        System.out.println(Math.incrementExact(x));
    }
}
```

**输出：**

```
Runtime Error :
Exception in thread "main" java.lang.ArithmeticException: integer overflow
    at java.lang.Math.incrementExact(Math.java:909)
    at Gfg2.main(File.java:13)
```