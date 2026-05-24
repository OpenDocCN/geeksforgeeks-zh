# Java `DoubleBinaryOperator` 接口示例

> 原文：[`https://www.geeksforgeeks.org/java-util-function-doublebinaryoperator-interface-with-examples/`](https://www.geeksforgeeks.org/java-util-function-doublebinaryoperator-interface-with-examples/)

在 Java 8 中引入了 `DoubleBinaryOperator` 接口。它表示对两个 `double` 值的操作，并将结果作为 `double` 值返回。这是一个[功能接口](https://www.geeksforgeeks.org/functional-interfaces-java/)，因此可以用作 lambda 表达式或方法引用。它主要用于需要从用户封装操作的时候。

## 方法

### `applyAsDouble()`

此函数接受两个双精度值，执行所需的操作，并将结果作为双精度值返回。

```java
public double applyAsDouble(double val1, double val2)
```

## 示例

将 `DoubleBinaryOperator` 接口演示为 [lambda 表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)的示例。

```java
// Java program to demonstrate DoubleBinaryOperator

import java.util.function.DoubleBinaryOperator;

public class DoubleBinaryOperatorDemo {
    public static void main(String[] args)
    {
        double x = 7.654;
        double y = 5.567;

// Representing addition as
        // the double binary operator
        DoubleBinaryOperator doubleBinaryOperator
            = (a, b) -> { return a + b; };
        System.out.println("x + y = "
                           + doubleBinaryOperator
                                 .applyAsDouble(x, y));

// Representing subtraction as
        // the double binary operator
        doubleBinaryOperator
            = (a, b) -> { return a - b; };
        System.out.println("x - y = "
                           + doubleBinaryOperator
                                 .applyAsDouble(x, y));

// Representing multiplication as
        // the double binary operator
        doubleBinaryOperator
            = (a, b) -> { return a * b; };
        System.out.println("x * y = "
                           + doubleBinaryOperator
                                 .applyAsDouble(x, y));

// Representing division as
        // the double binary operator
        doubleBinaryOperator
            = (a, b) -> { return a / b; };
        System.out.println("x / y = "
                           + doubleBinaryOperator
                                 .applyAsDouble(x, y));

// Representing remainder operation
        // as the double binary operator
        doubleBinaryOperator
            = (a, b) -> { return a % b; };
        System.out.println("x % y = "
                           + doubleBinaryOperator
                                 .applyAsDouble(x, y));
    }
}
```

## 输出

```java
x + y = 13.221
x - y = 2.0869999999999997
x * y = 42.609818000000004
x / y = 1.3748877312735763
x % y = 2.0869999999999997
```

## 参考

[`https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleBinaryOperator.html`](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleBinaryOperator.html)