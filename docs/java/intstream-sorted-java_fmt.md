# Java 中排序的 IntStream()

> 原文: [https://www.geeksforgeeks.org/intstream-sorted-java/](https://www.geeksforgeeks.org/intstream-sorted-java/)

## 概述

`IntStream sorted()` 返回一个由这个流的元素按排序顺序组成的流。这是一个有状态的中间操作，也就是说，在处理新元素时，它可能会包含来自以前看到的元素的状态。有状态的中间操作可能需要在产生结果之前处理整个输入。例如，在看到流的所有元素之前，无法对流进行排序。

## 语法

```java
IntStream sorted()
```

其中，`IntStream` 是一个原始 `int` 值元素的序列。这是 `Stream` 的 `int` 基本类型特化。

## 异常

如果该流的元素不可比较，则在执行终端操作时可能会抛出 `java.lang.ClassCastException`。

## 返回值

`IntStream sorted()` 方法返回新的流。

## 示例 1

使用 `IntStream sorted()` 对给定 `IntStream` 中的数字进行排序。

```java
// Java code to sort IntStream
// using IntStream.sorted()
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(10, 9, 8, 7, 6);

        // displaying the stream with sorted elements
        // using IntStream.sorted() function
        stream.sorted().forEach(System.out::println);
    }
}
```

**Output:**

```java

```

## 示例 2

使用 `IntStream sorted()` 对由 `IntStream.generate()` 生成的随机数进行排序。

```java
// Java code to sort IntStream
// using IntStream.sorted()
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream by generating
        // random elements using IntStream.generate()
        IntStream stream = IntStream.generate(()
                  -> (int)(Math.random() * 10000))
                  .limit(5);

        // displaying the stream with sorted elements
        // using IntStream.sorted() function
        stream.sorted().forEach(System.out::println);
    }
}
```

**Output:**

```java

```