# Java.util.function.LongBinaryOperator 接口示例

> 原文：[https://www.geeksforgeeks.org/java-util-function-longbinaryoperator-interface-with-examples/](https://www.geeksforgeeks.org/java-util-function-longbinaryoperator-interface-with-examples/)

在 Java 8 中引入了 `LongBinaryOperator` 接口。它表示对两个长值的操作，并将结果作为长值返回。这是一个[功能接口](https://www.geeksforgeeks.org/functional-interfaces-java/)，因此可以用作 `lambda` 表达式或方法引用。它主要用于需要从用户封装操作的时候。

## 方法

1.  `applyAsLong()`：此函数接受两个长值，执行所需的操作，并返回长值。

```java
public long applyAsLong(long val1, long val2)
```

将 `LongBinaryOperator` 接口演示为 `lambda` 表达式的示例。

```java
// Java program to demonstrate LongBinaryOperator

import java.util.function.LongBinaryOperator;

public class LongBinaryOperatorDemo {
    public static void main(String[] args)
    {

        LongBinaryOperator longBinaryOperator = (x, y) ->
        {
            return x + y;
        };

        System.out.print("343666 + 547477 = ");
        System.out.println(longBinaryOperator
                           .applyAsLong(343666, 547477));

        LongBinaryOperator longBinaryOperator1 = (x, y) ->
        {
            return x * y;
        };
        System.out.print("343666 * 547477 = ");
        System.out.println(longBinaryOperator1
                           .applyAsLong(343666, 547477));
    }
}
```

## 输出

```java
343666 + 547477 = 891143
343666 * 547477 = 188149230682
```

**参考：**[https://docs.oracle.com/javase/8/docs/api/java/util/function/LongBinaryOperator.html](https://docs.oracle.com/javase/8/docs/api/java/util/function/LongBinaryOperator.html)