# Java.util.function.IntBinaryOperator 接口带示例

> 原文：[https://www.geeksforgeeks.org/java-util-function-intbinaryoperator-interface-with-examples/](https://www.geeksforgeeks.org/java-util-function-intbinaryoperator-interface-with-examples/)

在 Java 8 中引入了`IntBinaryOperator`接口。它表示对两个 `int` 值的操作，并将结果作为 `int` 值返回。这是一个[功能接口](https://www.geeksforgeeks.org/functional-interfaces-java/)，因此可以用作 lambda 表达式或方法引用。它主要用于需要从用户封装操作的时候。

## 方法

1.  `applyAsInt()`：此函数接受两个 `Int` 值，执行所需的操作，并将结果作为 `int` 返回。

```java
public int applyAsInt(int val1, int val2)
```

用[λ表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)演示 `IntBinaryOperator` 接口的示例。

```java
// Java program to demonstrate IntBinaryOperator

import java.util.function.IntBinaryOperator;

public class IntBinaryOperatorDemo {
    public static void main(String[] args)
    {
        // Binary operator defined to divide
        // factorial of two numbers
        IntBinaryOperator binaryOperator = (x, y) ->
        {
            int fact1 = 1;
            for (int i = 2; i <= x; i++) {
                fact1 *= i;
            }
            int fact2 = 1;
            for (int i = 2; i <= y; i++) {
                fact2 *= i;
            }
            return fact1 / fact2;
        };

        System.out.println("5! divided by 7! = "
                           + binaryOperator.applyAsInt(5, 7));
        System.out.println("7! divided by 5! = "
                           + binaryOperator.applyAsInt(7, 5));
    }
}
```

## 输出

```java
5! divided by 7! = 0
7! divided by 5! = 42
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/function/IntBinaryOperator.html](https://docs.oracle.com/javase/8/docs/api/java/util/function/IntBinaryOperator.html)