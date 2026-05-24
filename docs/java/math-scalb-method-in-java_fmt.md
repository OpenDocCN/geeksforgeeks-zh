# Java 中的数学 scalb()方法

> 原文: [https://www.geeksforgeeks.org/math-scalb-method-in-java/](https://www.geeksforgeeks.org/math-scalb-method-in-java/)

## 1. `scalb(double a, int scale)` 方法

`scalb(double a, int scale)` 是 Java 中 `Math` 类的一个内置方法，用于获取值 `a * 2^scale`。当结果的指数介于 `Double.MIN_EXPONENT` 和 `Double.MAX_EXPONENT` 之间时，结果会被精确计算。它会产生四种特殊情况：
*   当结果的指数大于 `Double.MAX_VALUE` 时，它返回无穷大。
*   当第一个参数是 `NaN` 时，结果是 `NaN`。
*   当第一个参数为无穷大时，结果是同一个符号的无穷大。
*   当第一个参数为零时，它返回相同符号的零。

### 语法

```java
public static double scalb(double a, int scale)
```

### 参数

该方法接受两个参数，它们是：
*   `a`：这是双精度型，是要用 2 的幂来缩放的数。
*   `scale`：这是 2 的幂的整数型，用来缩放 `a`。

### 返回值

该方法返回 `a * 2^scale`。

### 示例

```java
Input: 
a = 77.23
scale = 3

Output = 617.84
```

下面的程序说明了 `java.lang.Math.scalb(double a, int scale)` 方法：

```java
// Java program to illustrate the
// java.lang.Math.scalb(double a, int scale )
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double p = 52.12;
        int scale = 8;

        // It returns p x 2^scale
        System.out.print("Value of Math.scalb(" 
                         + p + ", " + scale + ") = ");
        System.out.println(Math.scalb(p, scale));
    }
}
```

### 输出

```java
Value of Math.scalb(52.12, 8) = 13342.72
```

## 2. `java.lang.Math.scalb(float a, int scale)` 方法

`java.lang.Math.scalb(float a, int scale)` 是一个内置方法，它返回 `a * 2^scale`。当结果的指数介于 `Float.MIN_EXPONENT` 和 `Float.MAX_EXPONENT` 之间时，结果会被精确计算。
*   当结果的指数大于 `Float.MAX_VALUE` 时，它返回无穷大。
*   当第一个参数是 `NaN` 时，结果是 `NaN`。
*   当第一个参数为无穷大时，结果是同一个符号的无穷大。
*   当第一个参数为零时，它返回相同符号的零。

### 语法

```java
public static double scalb(float a, int scale)
```

### 参数

该方法接受两个参数：
*   `a`：这是浮点型的，是要用 2 的幂来缩放的数字。
*   `scale`：整数型，是指 `a` 缩放中使用的 2 的幂。

### 返回值

该方法返回 `a * 2^scale`。

### 示例

```java
Input: 
a = 32.14f
scale = 6

Output = 2056.96
```

下面的程序说明了 `java.lang.Math.scalb(float a, int scale)` 方法：

### 程序 1

```java
// Java program to illustrate the
// java.lang.Math.scalb(float a, int scale )
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        float p = 81.27f;
        int scale = 8;

        // Calculate p multiplied by 2 raised in scale
        System.out.print("Value of Math.scalb(" +
                         p + ", " + scale + ") = ");
        System.out.println(Math.scalb(p, scale));
    }
}
```

### 输出

```java
Value of Math.scalb(81.27, 8) = 20805.12
```