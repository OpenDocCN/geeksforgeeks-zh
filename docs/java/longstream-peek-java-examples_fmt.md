# Java 中的 LongStream peek()，带示例

> 原文: [https://www.geeksforgeeks.org/longstream-peek-java-examples/](https://www.geeksforgeeks.org/longstream-peek-java-examples/)

`LongStream peek()` 是 `java.util.stream.LongStream` 中的一个方法，该函数返回一个由这个流的元素组成的流，当从结果流中消费元素时，还会对每个元素执行提供的操作。

## 语法:

```java
LongStream peek(LongConsumer action)
```

其中，`LongStream` 是一个原始 `long` 值元素的序列，该方法返回一个并行的 `LongStream`，`LongConsumer` 表示一个接受单个 `long` 值参数的操作。

## 示例 1 : 对给定范围的流执行求和。

```java
// Java code for LongStream peek()
// where the action performed is to get
// sum of all elements in given range
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a stream of longs
        LongStream stream = LongStream.range(2L, 10L);

        // performing action sum on elements of
        // given range and storing the result in sum
        long sum = stream.peek(System.out::println).sum();

        // Displaying the result of action performed
        System.out.println("sum is : " + sum);
    }
}
```

## 输出:

```java
sum is : 44
```