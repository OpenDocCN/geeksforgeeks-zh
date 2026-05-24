# Java 中的 LongToIntFunction 接口示例

> 原文：[https://www.geeksforgeeks.org/longtointfunction-interface-in-java-with-examples/](https://www.geeksforgeeks.org/longtointfunction-interface-in-java-with-examples/)

## LongToIntFunction 接口简介

`LongToIntFunction` 接口是从 Java 8 开始引入的 `java.util.function` 包的一部分，用于在 Java 中实现[函数式编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个接受 `long` 值参数并给出 `int` 值结果的函数。

分配给 `LongToIntFunction` 类型的对象的 Lambda 表达式用于定义其 `applyAsInt()` 方法，该表达式最终将给定的操作应用于其唯一的参数。这类似于使用类型为 `Function<Long, Integer>` 的对象。

`LongToIntFunction` 接口只有一个功能方法：

### applyAsInt() 方法

此方法接受 `long` 值参数并给出一个 `int` 值结果。

**语法：**

```java
int applyAsInt(long value)
```

**参数：** 此方法接受一个参数 `value`，这是 `long` 值参数。

**返回：** 该方法返回一个 `int` 值结果。

下面是说明 `applyAsInt()` 方法的代码：

**程序**

```java
// Java Program to demonstrate
// LongToIntFunction's applyAsInt() method

import java.util.function.LongToIntFunction;

public class Main {
    public static void main(String args[])
    {
        // Instantiating LongToIntFunction
        LongToIntFunction ob = a -> (int)a * 100000;

        // Applying the above function
        // using applyAsInt()
        System.out.println(ob.applyAsInt(2));
    }
}
```

**输出：**

```java

```