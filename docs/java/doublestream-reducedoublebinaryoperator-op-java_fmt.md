# Java 中的 DoubleStream reduce(DoubleBinaryOperator op)

> 原文: [https://www.geeksforgeeks.org/doublestream-reducedoublebinaryoperator-op-java/](https://www.geeksforgeeks.org/doublestream-reducedoublebinaryoperator-op-java/)

## 概述

`DoubleStream` 的 `reduce(DoubleBinaryOperator op)` 方法使用一个**关联**的累积函数对该流的元素执行缩减操作，并返回一个描述缩减值的 `OptionalDouble`（如果存在）。

一个**约简操作**（或**折叠**）接收一个输入元素序列，并将它们组合成一个单一的汇总结果，例如计算一组数字的和或最大值。如果满足以下条件，则运算符或函数 `op` 是关联的：

```java
(a op b) op c == a op (b op c)
```

这是一个**终端操作**，这意味着它可能会遍历流以产生结果或副作用。执行终端操作后，流管道即被视为已消耗，无法再使用。

## 语法

```java
OptionalDouble reduce(DoubleBinaryOperator op)
```

## 参数

*   `op`: 用于组合两个值的关联无状态函数，其类型为 `DoubleBinaryOperator`。`DoubleBinaryOperator` 是对两个 `double` 值操作数进行运算并产生 `double` 值结果的函数。

## 返回值

一个描述减少的值（如果存在）的 `OptionalDouble`。`OptionalDouble` 是一个可能包含也可能不包含 `double` 值的容器对象。如果存在值，`isPresent()` 将返回 `true`，`getAsDouble()` 将返回该值。

## 示例 1

```java
// Java code for DoubleStream reduce
// (DoubleBinaryOperator op)
import java.util.OptionalDouble;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = DoubleStream.of(1.2, 2.3, 3.4, 4.5);

        // Using OptionalDouble (a container object which
        // may or may not contain a non-null value)
        // Using DoubleStream reduce(DoubleBinaryOperator op)
        OptionalDouble answer = stream.reduce(Double::sum);

        // if the stream is empty, an empty
        // OptionalDouble is returned.
        if (answer.isPresent()) {
            System.out.println(answer.getAsDouble());
        }
        else {
            System.out.println("Stream is empty");
        }
    }
}
```

输出：

```java
11.4
```

## 示例 2

```java
// Java code for DoubleStream reduce
// (DoubleBinaryOperator op)
import java.util.OptionalDouble;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = DoubleStream.of(1.2, 2.3, 3.4, 4.5);

        // Using OptionalDouble (a container object which
        // may or may not contain a non-null value)
        // Using DoubleStream reduce(DoubleBinaryOperator op)
        OptionalDouble answer = stream.reduce((a, b)
                              -> (a * b) * (a * b));

        // if the stream is empty, an empty
        // OptionalDouble is returned.
        if (answer.isPresent()) {
            System.out.println(answer.getAsDouble());
        }
        else {
            System.out.println("Stream is empty");
        }
    }
}
```

输出：

```java
9111992.471343633
```