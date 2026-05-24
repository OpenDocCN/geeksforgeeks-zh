# 如何在 Java 中获取一个流的切片

> 原文：[https://www.geeksforgeeks.org/how-to-get-slice-of-a-stream-in-java/](https://www.geeksforgeeks.org/how-to-get-slice-of-a-stream-in-java/)

一个[流](https://www.geeksforgeeks.org/stream-in-java/)是一个支持各种方法的对象序列，这些方法可以被流水线化以产生期望的结果。**一条流的切片**是指从原始流中存在于指定界限内的元素流。

**示例：**

> **输入：**【11、12、13、14、15、16、17、18、19、20】
> **输出：**【15、16、17、18、19】
> **解释：**输出包含从索引 4 到 8 的流的一个切片。
>
> **输入：**【1，2，3，4，5，6，7，8，9】
> **输出：**【2，3，4】
> **解释：**输出包含从索引 1 到 3 的流的切片。

以下是在 Java 中从列表中移除空值的方法：

## 1. 使用 `skip()` 和 `limit()`

[Stream API in Java](https://www.geeksforgeeks.org/stream-in-java/) 提供 `skip()` 方法，用于丢弃流中不需要的元素。它还提供 `limit()` 函数，用于获取具有指定索引作为限制的新流，按遇到的顺序。

**算法：**

1.  获取要切片的流。
2.  获取要从流中切片的“从”和“到”索引，作为**开始索引**和**结束索引**。
3.  调用 `skip()` 方法，将起始索引前要跳过的元素个数指定为 `skip(startIndex)`。
4.  调用 `limit()` 方法从流中指定元素的数量，该数量应被限制为 `limit(endIndex - startIndex + 1)`。
5.  返回**切片流**。

```java
// Java program to get slice of a stream using
// Stream skip() and limit()
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Generic function to get Slice of a
    // Stream from startIndex to endIndex
    public static <T> Stream<T>
    getSliceOfStream(Stream<T> stream, int startIndex, int endIndex)
    {
        return stream
            // specify the number of elements to skip
            .skip(startIndex)
            // specify the no. of elements the stream
            // that should be limited
            .limit(endIndex - startIndex + 1);
    }

    public static void main(String[] args)
    {
        // Create a new List with values 11 - 20
        List<Integer> list = new ArrayList<>();
        for (int i = 11; i <= 20; i++)
            list.add(i);

        // Create stream from list
        Stream<Integer> intStream = list.stream();

        // Print the stream
        System.out.println("List: " + list);

        // Get Slice of Stream
        // containing of elements from the 4th index to 8th
        Stream<Integer>
            sliceOfIntStream = getSliceOfStream(intStream, 4, 8);

        // Print the slice
        System.out.println("\nSlice of Stream:");
        sliceOfIntStream.forEach(System.out::println);
    }
}
```

**输出：**

```java
List: [11, 12, 13, 14, 15, 16, 17, 18, 19, 20]

Slice of Stream:
15
16
17
18
19
```

## 2. 使用 `Collectors` 结合 `skip()` 和 `limit()`

在此方法中，流被转换为列表，然后使用收集器的函数来获取所需元素的子列表，最后使用 `stream.collect(Collectors.collectingAndThen())` 将子列表转换回流。

**算法：**

1.  获取要切片的流。
2.  获取要从流中切片的“从”和“到”索引，作为**开始索引**和**结束索引**。
3.  使用 `Collectors.collectingAndThen()`。
4.  使用 `Collectors.toList()` 将流转换为列表。
5.  从列表中获取流作为 `list.stream()`。
6.  调用 `skip()` 方法，将起始索引前要跳过的元素个数指定为 `skip(startIndex)`。
7.  调用 `limit()` 方法从流中指定元素的数量，该数量应被限制为 `limit(endIndex - startIndex + 1)`。
8.  使用 `stream.collect()` 收集切片列表流。
9.  返回**切片流**。

```java
// Java program to get slice of a stream using
// Collection skip() and limit()
import java.util.*;
import java.util.stream.*;

class GFG {

    // Generic function to get Slice of a
    // Stream from startIndex to endIndex
    public static <T> Stream<T>
    getSliceOfStream(Stream<T> stream, int startIndex, int endIndex)
    {
        return stream.collect(Collectors.collectingAndThen(
            // 1st argument
            // Convert the stream to list
            Collectors.toList(),
            // 2nd argument
            list -> list.stream()
                        // specify the number of elements to skip
                        .skip(startIndex)
                        // specify the no. of elements the stream
                        // that should be limited
                        .limit(endIndex - startIndex + 1)));
    }

    public static void main(String[] args)
    {
        // Create a new List with values 11 - 20
        List<Integer> list = new ArrayList<>();
        for (int i = 11; i <= 20; i++)
            list.add(i);

        // Create stream from list
        Stream<Integer> intStream = list.stream();

        // Print the stream
        System.out.println("List: " + list);

        // Get Slice of Stream
        // containing of elements from the 4th index to 8th
        Stream<Integer>
            sliceOfIntStream = getSliceOfStream(intStream, 4, 8);

        // Print the slice
        System.out.println("\nSlice of Stream:");
        sliceOfIntStream.forEach(System.out::println);
    }
}
```

**输出：**

```java
List: [11, 12, 13, 14, 15, 16, 17, 18, 19, 20]

Slice of Stream:
15
16
17
18
19
```

## 3. 获取 `SubList`

此方法涉及将流转换为列表。然后使用此列表在指定索引之间获取所需的子列表。最后，将此子列表转换回流。

**算法：**

1.  获取要切片的流。
2.  获取要从流中切片的“从”和“到”索引，作为**开始索引**和**结束索引**。
3.  使用 `Collectors.toList()` 将流转换为列表，然后使用 `stream.collect()` 进行收集。
4.  使用 `subList(startIndex, endIndex + 1)` 从收集的列表中获取以开始索引和结束索引+1 为限制的子列表。
5.  使用 `stream()` 将子列表转换回流。
6.  返回**切片流**。

```java
// Java program to get slice of a stream by
// fetching a sublist
import java.util.*;
import java.util.stream.*;

class GFG {

    // Generic function to get Slice of a
    // Stream from startIndex to endIndex
    public static <T> Stream<T>
    getSliceOfStream(Stream<T> stream, int startIndex, int endIndex)
    {
        return stream
            // Convert the stream to list
            .collect(Collectors.toList())
            // Fetch the subList between the specified index
            .subList(startIndex, endIndex + 1)
            // Convert the subList to stream
            .stream();
    }

    public static void main(String[] args)
    {
        // Create a new List with values 11 - 20
        List<Integer> list = new ArrayList<>();
        for (int i = 11; i <= 20; i++)
            list.add(i);

        // Create stream from list
        Stream<Integer> intStream = list.stream();

        // Print the stream
        System.out.println("List: " + list);

        // Get Slice of Stream
        // containing of elements from the 4th index to 8th
        Stream<Integer>
            sliceOfIntStream = getSliceOfStream(intStream, 4, 8);

        // Print the slice
        System.out.println("\nSlice of Stream:");
        sliceOfIntStream.forEach(System.out::println);
    }
}
```

**输出：**

```java
List: [11, 12, 13, 14, 15, 16, 17, 18, 19, 20]

Slice of Stream:
15
16
17
18
19
```