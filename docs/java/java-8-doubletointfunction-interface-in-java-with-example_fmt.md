# Java 8 中的 DoubleToIntFunction 接口及示例

> 原文：[https://www.geeksforgeeks.org/java-8-doubletointfunction-interface-in-java-with-example/](https://www.geeksforgeeks.org/java-8-doubletointfunction-interface-in-java-with-example/)

`DoubleToIntFunction` 接口是从 Java 8 开始引入的 `java.util.function` 包的一部分，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个接受双精度值参数并给出整型值结果的函数。

分配给 `DoubleToIntFunction` 类型的对象的 Lambda 表达式用于定义其 `applyAsInt()` 方法，该方法最终对其唯一的参数应用给定的操作。这类似于使用类型为 `Function<Double, Integer>` 的对象。

`DoubleToIntFunction` 接口只有一个功能方法：

`applyAsInt()`：这个方法接受一个双精度值参数并给出一个 `int` 值结果。

### 语法

```java
int applyAsInt(double value)
```

**参数：** 该方法接受一个参数 `value`，该值是作为整数应用的双精度值参数。

**返回：** 该方法返回一个 `int` 值结果。

下面是说明 `applyAsInt()` 方法的代码：

### 程序

```java
// Java Program to demonstrate
// DoubleToIntFunction's applyAsInt() method

import java.util.function.DoubleToIntFunction;

public class Main {
    public static void main(String args[])
    {
        // Create a DoubleToIntFunction
        DoubleToIntFunction truncate = a -> (int)a;

        // Apply the function using applyAsInt()
        System.out.println(truncate.applyAsInt(10.6));
    }
}
```

### 输出

```java
10
```