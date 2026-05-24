# Java 中的 IntUnaryOperator 映射器

> 原文：[https://www.geeksforgeeks.org/intstream-mapintunaryoperator-mapper-java/](https://www.geeksforgeeks.org/intstream-mapintunaryoperator-mapper-java/)

`IntStream map(IntUnaryOperator mapper)`返回一个流，该流由给定函数应用于该流元素的结果组成。这是一个**中间操作**。这些操作总是懒惰的。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**语法：**

```java
IntStream map(IntUnaryOperator mapper)
```

**参数：**

1.  `IntStream`：一系列原始的 `int` 值元素。
2.  `IntUnaryOperator`：对单个整型值操作数进行运算，产生整型值结果。
3.  `mapper`：应用于每个元素的无状态函数，该函数返回新的流。

**返回值：** `IntStream map(IntUnaryOperator mapper)`通过应用给定的函数返回一个流。

**例 1：** 利用 `IntStream map()` 得到 `IntStream` 元素平方的负值。

```java
// Java code for IntStream map
// (IntUnaryOperator mapper) to get a
// stream by applying the given function.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

// Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream1 = IntStream.of(4, 5, 6, 7);

        // Using IntStream map()
        IntStream stream2 = stream1.map(num -> (-num * num));

        // Displaying the resulting IntStream
        stream2.forEach(System.out::println);
    }
}
```

**Output：**

```java

```

**例 2：** 利用 `IntStream map()` 得到给定范围内 `IntStream` 的一半元素。

```java
// Java code for IntStream map
// (IntUnaryOperator mapper) to get a
// stream by applying the given function.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

// Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream in range [2, 7)
        IntStream stream1 = IntStream.range(2, 7);

        // Using IntStream map()
        IntStream stream2 = stream1.map(num -> (num / 2));

        // Displaying the resulting IntStream
        stream2.forEach(System.out::println);
    }
}
```

**Output：**

```java

```