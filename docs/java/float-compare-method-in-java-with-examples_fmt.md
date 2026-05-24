# Java 中的 `Float.compare()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/float-compare-method-in-java-with-examples/](https://www.geeksforgeeks.org/float-compare-method-in-java-with-examples/)

`Float` 类的 `compare()` 方法是 Java 中的一个内置方法，用于比较两个指定的浮点值。返回的整数值的符号与函数调用返回的整数的符号相同。

## 语法

```java
public static int compare(float f1, float f2)
```

## 参数

该函数接受两个参数：

*   `f1`：要比较的第一个浮点值。
*   `f2`：要比较的第二个浮点值。

## 返回值

函数返回值如下：

*   `0`：如果 `f1` 在数值上等于 `f2`。
*   负值：如果 `f1` 数值小于 `f2`。
*   正值：如果 `f1` 在数值上大于 `f2`。

下面的程序说明了 `Float.compare()` 函数的使用：

## 程序 1：当两个整数相同时

```java
// Java Program to illustrate
// the Float.compare() method

import java.lang.Float;

public class GFG {
    public static void main(String[] args)
    {

        // Get the two float values
        // to be compared
        Float f1 = 1023f;
        Float f2 = 1023f;

        // function call to compare two float values
        if (Float.compare(f1, f2) == 0) {

            System.out.println("f1=f2");
        }
        else if (Float.compare(f1, f2) < 0) {

            System.out.println("f1<f2");
        }
        else {

            System.out.println("f1>f2");
        }
    }
}
```

**Output:**

```java
f1=f2
```

## 程序 2：当 `f1 < f2`

```java
// Java Program to illustrate
// the Float.compare() method

import java.lang.Float;

public class GFG {
    public static void main(String[] args)
    {

        // Get the two float values
        // to be compared
        Float f1 = 10f;
        Float f2 = 1023f;

        // function call to compare two float values
        if (Float.compare(f1, f2) == 0) {

            System.out.println("f1=f2");
        }
        else if (Float.compare(f1, f2) < 0) {

            System.out.println("f1<f2");
        }
        else {

            System.out.println("f1>f2");
        }
    }
}
```

**Output:**

```java
f1<f2
```

## 程序 3：当 `f1 > f2`

```java
// Java Program to illustrate
// the Float.compare() method

import java.lang.Float;

public class GFG {
    public static void main(String[] args)
    {

        // Get the two float values
        // to be compared
        Float f1 = 1023f;
        Float f2 = 10f;

        // function call to compare two float values
        if (Float.compare(f1, f2) == 0) {

            System.out.println("f1=f2");
        }
        else if (Float.compare(f1, f2) < 0) {

            System.out.println("f1<f2");
        }
        else {

            System.out.println("f1>f2");
        }
    }
}
```

**Output:**

```java
f1>f2
```

**参考**：[https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#compare(float, %20float)](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#compare(float, %20float))