# Java Math log()方法示例

> 原文: [https://www.geeksforgeeks.org/java-math-log-method-example/](https://www.geeksforgeeks.org/java-math-log-method-example/)

`java.lang.Math.log()` 方法返回一个双精度值的自然对数(以 e 为底)作为参数。有各种情况:

*   如果参数是 `nan` 或小于零，则结果是 `nan`。
*   如果自变量是 `positive infinity`，则结果是 `positive infinity`。
*   如果自变量是 `positive zero` 或 `negative zero`，结果是 `negative infinity`。

## 语法

```java
public static double log(double a)
```

## 参数

```java
a : User input
```

## 返回

```java
This method returns the value ln a.
```

## 示例

展示 `java.lang.Math.log()` 方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.log() method
import java.lang.Math;

class Gfg {

// driver code
    public static void main(String args[])
    {

double a = -2.55;
        double b = 1.0 / 0;
        double c = 0, d = 145.256;

// negative integer as argument, output NAN
        System.out.println(Math.log(a));

// positive infinity as argument, output Infinity
        System.out.println(Math.log(b));

// positive zero as argument, output -Infinity
        System.out.println(Math.log(c));

// positive double as argument
        System.out.println(Math.log(d));

}
}
```

## 输出

```java
NaN
Infinity
-Infinity
4.978497702968366
```