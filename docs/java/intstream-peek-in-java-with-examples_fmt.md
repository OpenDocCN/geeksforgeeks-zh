# Java 中的 IntStream peek()，带示例

> 原文：[https://www.geeksforgeeks.org/intstream-peek-in-java-with-examples/](https://www.geeksforgeeks.org/intstream-peek-in-java-with-examples/)

`IntStream peek()` 是 `java.util.stream.IntStream` 中的一个方法，该函数返回一个由这个流的元素组成的流，当元素从结果流中被消耗掉时，还会对每个元素执行提供的操作。

## 语法

```java
IntStream peek(IntConsumer action)
```

其中，`IntStream` 是一个原始 `int` 值元素的序列，该函数返回一个并行的 `IntStream`，而 `IntConsumer` 表示一个接受单个 `int` 值参数的操作。

## 示例 1：对给定范围的流执行求和

```java
// Java code for IntStream peek()
// where the action performed is to get
// sum of all elements in given range
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args) {

        // Creating a stream of integers
        IntStream stream = IntStream.range(2, 10);

        // performing action sum on elements of
        // given range and storing the result in sum
        int sum = stream.peek(System.out::println).sum();

        // Displaying the result of action performed
        System.out.println("sum is : " + sum);
    }
}
```

输出：

```java
sum is : 44
```

## 示例 2：对给定范围的流执行计数操作

```java
// Java code for IntStream peek()
// where the action performed is to get
// count of all elements in given range
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args) {

        // Creating a stream of integers
        IntStream stream = IntStream.range(2, 10);

        // performing action count on elements of
        // given range and storing the result in Count
        long Count = stream.peek(System.out::println).count();

        // Displaying the result of action performed
        System.out.println("count : " + Count);
    }
}
```

输出：

```java
count : 8
```

## 示例 3：对给定范围的流执行平均运算

```java
// Java code for IntStream peek()
// where the action performed is to get
// average of all elements in given range
import java.util.*;
import java.util.OptionalDouble;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args) {

        // Creating a stream of integers
        IntStream stream = IntStream.range(2, 10);

        // performing action average on elements of
        // given range and storing the result in avg
        OptionalDouble avg = stream.peek(System.out::println)
                            .average();

        // If a value is present, isPresent()
        // will return true, else -1 is displayed.
        if(avg.isPresent())
        {
            System.out.println("Average is : " + avg.getAsDouble());
        }
        else
        {
            System.out.println("-1");
        }
    }
}
```

输出：

```java
Average is : 5.5
```