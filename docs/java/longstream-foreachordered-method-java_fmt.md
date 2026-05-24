# Java 中的 LongStream forEachOrdered()方法

> 原文: [https://www.geeksforgeeks.org/longstream-foreachordered-method-java/](https://www.geeksforgeeks.org/longstream-foreachordered-method-java/)

`LongStream forEachOrdered(LongConsumer action)` 按照遭遇顺序对该流的每个元素执行一个操作。`LongStream forEachOrdered(LongConsumer action)` 是一种**终端操作**，即它可能会遍历流以产生结果或副作用。

## 语法

```java
void forEachOrdered(LongConsumer action)
```

## 参数

`LongConsumer` 表示接受单个长值参数且不返回结果的操作。这是 `Long` 原始类型的消费者专业化。

## 注意

`forEachOrdered(LongConsumer action)` 对该流的每个元素执行一个操作，在流的**相遇顺序**中，如果该流具有定义的相遇顺序。

## 例 1

```java
// Java code for LongStream forEachOrdered
// (LongConsumer action) in Java 8
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(2L, 3L, 4L, 5L);

        // Using LongStream.forEachOrdered
        stream.forEachOrdered(System.out::println);
    }
}
```

**Output:**

```java

```

## 例 2

```java
// Java code for LongStream forEachOrdered
// (LongConsumer action) in Java 8
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.range(5L, 11L);

        // Using LongStream.forEachOrdered() on
        // sequential stream
        stream.forEachOrdered(System.out::println);
    }
}
```

**Output:**

```java

```

## 例 3

```java
// Java code for LongStream forEachOrdered
// (LongConsumer action) in Java 8
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.range(5, 11);

        // Using LongStream.forEachOrdered() on
        // parallel stream
        stream.parallel().forEachOrdered(System.out::println);
    }
}
```

**输出:**

```java

```