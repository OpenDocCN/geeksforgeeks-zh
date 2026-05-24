# Java 8 IntToDoubleFunction 接口详解（含示例）

> 原文：[https://www.geeksforgeeks.org/java-8-inttodoublefunction-interface-in-java-with-examples/](https://www.geeksforgeeks.org/java-8-inttodoublefunction-interface-in-java-with-examples/)

`IntToDoubleFunction` 接口是 Java 8 开始引入的 `java.util.function` 包的一部分，用于在 Java 中实现[函数式编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个接受整型参数并给出双值结果的函数。

分配给 `IntToDoubleFunction` 类型的对象的 Lambda 表达式用于定义其 `applyAsDouble()` 方法，该方法最终将给定的操作应用于其唯一的参数。这类似于使用类型为 `Function<Integer, Double>` 的对象。

`IntToDoubleFunction` 接口只有一个功能方法：

## `applyAsDouble()`

此方法接受一个 `int` 值参数，并给出一个 `double` 值结果。

### 语法

```java
double applyAsDouble(int value)
```

### 参数

此方法接受一个参数 `value`，这是整数值参数。

### 返回值

该方法返回一个 `double` 值结果。

下面是演示 `applyAsDouble()` 方法的代码：

### 示例程序

```java
// Java Program to demonstrate
// IntToDoubleFunction's applyAsDouble() method

import java.util.function.IntToDoubleFunction;

public class Main {
    public static void main(String args[]) {
        // Declare IntToDoubleFunction
        IntToDoubleFunction func = a -> 3.12 * a;

        // Apply the function to get the result as double
        // using applyAsDouble()
        System.out.println(func.applyAsDouble(2));
    }
}
```

### 输出

```java
6.24
```