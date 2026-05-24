# Java 中的 DoubleStream reduce 方法（double identity, DoubleBinaryOperator op）示例

> 原文：[https://www.geeksforgeeks.org/doublestream-reducedouble-identity-doublebinaryoperator-op-java/](https://www.geeksforgeeks.org/doublestream-reducedouble-identity-doublebinaryoperator-op-java/)

`DoubleStream reduce(double identity, DoubleBinaryOperator op)` 使用提供的 `identity` 值和关联累加函数对该流的元素执行约简，并返回约简后的值。

一个**约简操作**或**折叠**取一个输入元素序列，并把它们组合成一个单一的汇总结果，比如求一组数字的和或最大值。如果满足以下条件，则运算符或函数 `op` 是关联的：

```java
(a op b) op c == a op (b op c)
```

这是一个**终端操作**，也就是说，它可能会遍历流以产生结果或副作用。执行终端操作后，流管道被认为已消耗，不能再使用。

## 语法

```java
double reduce(double identity, DoubleBinaryOperator op)
```

## 参数

*   `identity`：累加函数的标识值。
*   `DoubleBinaryOperator`：对两个 `double` 值操作数进行运算并产生 `double` 值结果。
*   `op`：用于组合两个值的关联无状态函数。

## 返回值

约简的结果。

## 例 1

```java
// Java code for DoubleStream reduce
// (double identity, DoubleBinaryOperator op)
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = DoubleStream.of(1.2, 2.3,
                                              3.4, 4.5, 5.6);

        // Using DoubleStream reduce
        // (double identity, DoubleBinaryOperator op)
        double answer = stream.reduce(5, (num1, num2)
                                             -> (num1 + num2));

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出：

```java
22.0
```

## 例 2

```java
// Java code for DoubleStream reduce
// (double identity, DoubleBinaryOperator op)
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = DoubleStream.of(2.1, 3.2,
                                              4.3, 5.4, 6.5);

        // Using DoubleStream reduce
        // (double identity, DoubleBinaryOperator op)
        double answer = stream.reduce(3, (num1, num2)
                                             -> (num1 * num2) * 2);

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出：

```java
97367.96160000002
```