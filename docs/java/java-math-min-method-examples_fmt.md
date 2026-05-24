# Java Math.min() 方法详解与示例

> 原文：[https://www.geeksforgeeks.org/java-math-min-method-examples/](https://www.geeksforgeeks.org/java-math-min-method-examples/)

`java.lang.Math.min()` 函数是 Java 中的一个内置函数，返回两个数字的最小值。参数类型可以是 `int`、`double`、`float` 和 `long`。如果一个负数和一个正数作为参数传递，则返回负数结果。如果传递的两个参数都是负数，那么结果会返回绝对值较大的那个数（即数值更小的负数）。

## 语法

```java
dataType min(dataType num1, dataType num2)
```

`dataType` 可以是 `int`、`float`、`double` 或 `long`。

**参数：** 该函数接受两个参数 `num1` 和 `num2`，并返回其中的最小值。

## 返回值

函数返回两个数字的最小值。返回值的数据类型与参数的数据类型相同。

下面是 `min()` 函数的示例：

## 示例 1：比较两个双精度数

```java
// Java program to demonstrate the
// use of min() function
// two double data-type numbers are passed as argument
public class Gfg {

    public static void main(String args[])
    {
        double a = 12.123;
        double b = 12.456;

        // prints the minimum of two numbers
        System.out.println(Math.min(a, b));
    }
}
```

**输出：**

```java
12.123
```

## 示例 2：比较一个正数和一个负数

```java
// Java program to demonstrate the
// use of min() function
// when one positive and one
// negative integers are passed as argument
public class Gfg {

    public static void main(String args[])
    {
        int a = 23;
        int b = -23;

        // prints the minimum of two numbers
        System.out.println(Math.min(a, b));
    }
}
```

**输出：**

```java
-23
```

## 示例 3：比较两个负数

```java
// Java program to demonstrate
// the use of min() function
// when two negative integers
// are passed as argument
public class Gfg {

    public static void main(String args[])
    {
        int a = -25;
        int b = -23;

        // prints the minimum of two numbers
        System.out.println(Math.min(a, b));
    }
}
```

**输出：**

```java
-25
```

如果你想在代码中多次找到两个数字的最小值，那么每次写完整的 `Math.min()` 往往会很繁琐。所以这里一个更短更省时的方法是直接将 `java.lang.Math.min` 导入为静态，然后只使用 `min()` 代替完整的 `Math.min()`。

## 示例 4：静态导入

```java
import static java.lang.Math.min;

class GFG {
    public static void main(String[] args)
    {
        int a = 3;
        int b = 4;
        System.out.println(min(a, b));
    }
}
```

**输出：**

```java
3
```