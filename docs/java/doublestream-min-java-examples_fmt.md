# Java 中的 DoubleStream min()，示例

> 原文：[https://www.geeksforgeeks.org/doublestream-min-java-examples/](https://www.geeksforgeeks.org/doublestream-min-java-examples/)

`java.util.stream.DoubleStream` 在 Java 8 中被引入，用于处理原生的 `double` 值流。它以一种新的方式解决了求数组中的最大值、最小值、所有元素的和以及平均值等问题。`DoubleStream min()` 方法返回一个描述该流最小元素的 `OptionalDouble`，如果该流为空，则返回一个空的 `OptionalDouble`。

## 语法

```java
OptionalDouble min()
```

其中，`OptionalDouble` 是一个容器对象，它可能包含也可能不包含一个 `double` 值。

## 注意

1.  与数值比较运算符不同，该方法认为负零（`-0.0`）严格小于正零（`+0.0`）。
2.  这是 `reduce` 操作的一个特例。

## 例 1

```java
// Java code for DoubleStream min()
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream
        DoubleStream stream = DoubleStream.of(-9.5,
                   -18.6, 54.3, 8.5, 7.4, 14.2, 3.9);

        // OptionalDouble is a container object
        // which may or may not contain a
        // double value.
        OptionalDouble obj = stream.min();

        // If a value is present, isPresent() will
        // return true and getAsDouble() will
        // return the value
        if (obj.isPresent()) {
            System.out.println(obj.getAsDouble());
        }
        else {
            System.out.println("-1");
        }
    }
}
```

输出：

```java
-18.6
```

## 例 2

```java
// Java code for DoubleStream min()
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // OptionalDouble is a container object
        // which may or may not contain a
        // double value.
        OptionalDouble obj = DoubleStream.empty().min();

        // If a value is present, isPresent() will
        // return true and getAsDouble() will
        // return the value
        if (obj.isPresent()) {
            System.out.println(obj.getAsDouble());
        }
        else {
            System.out.println("-1");
        }
    }
}
```

输出：

```java

```