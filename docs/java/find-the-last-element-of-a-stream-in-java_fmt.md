# 在 Java 中找到一个流的最后一个元素

> 原文: [https://www.geeksforgeeks.org/find-the-last-element-of-a-stream-in-java/](https://www.geeksforgeeks.org/find-the-last-element-of-a-stream-in-java/)

给定一个包含一些元素的`流`，任务是在 Java 中获取流的最后一个元素。

**示例:**

> **输入:** 流 = {“Geek_First”, “Geek_2”, “Geek_3”, “Geek_4”, “Geek_Last”}
> **输出:** Geek_Last
>
> **输入:** 流 = {1, 2, 3, 4, 5, 6, 7}
> **输出:** 7

在流中查找最后一个元素的方法有很多:

## 1. 使用 `Stream.reduce()` 方法

`reduce` 方法作用于流中的两个元素，并根据所需条件返回元素。因此，此方法可用于缩减流，使其仅包含最后一个元素。

**思路:**

*   获取要返回最后一个元素的元素流。
    *   要获得最后一个元素，可以使用 `reduce()` 方法忽略第一个元素，重复操作，直到没有第一个元素。

```java
Stream.reduce((first, second) -> second)
```

*   这将一个流中的一组元素简化为单个元素，也就是最后一个。
    *   因此，唯一的单个元素将保留在流中，这是最后一个元素。

以下是上述方法的实现:

**示例:**

```java
// Java program to find last
// element of a Stream in Java

import java.util.*;
import java.util.stream.*;

public class GFG {

    // Function to find the
    // last_elements in a Stream
    public static <T> T
    lastElementInStream(Stream<T> stream)
    {
        T last_element
            = stream

            // reduce() method reduces the Stream
            // to a single element, which is last.
            .reduce((first, second) -> second)

            // if stream is empty
            // null is returned
            .orElse(null);

        return last_element;
    }

    // Driver code
    public static void main(String[] args)
    {

        Stream<String> stream
            = Stream.of("Geek_First", "Geek_2",
                        "Geek_3", "Geek_4",
                        "Geek_Last");

        // Print the last element of a Stream
        System.out.println(
            "Last Element: "
            + lastElementInStream(stream));
    }
}
```

**输出:**

```java
Last Element: Geek_Last
```

## 2. 使用 `Stream.skip()` 方法

`skip()` 方法在移除前 N 个元素后返回一个流。因此，此方法可用于跳过除最后一个元素外的所有元素。

**思路:**

*   获取要返回最后一个元素的元素流。
    *   要获取最后一个元素，可以使用 `skip()` 方法和 `count()` 方法。

```java
Stream.skip(stream.count()-1)
```

*   这将在移除第一个 `count()-1` 个元素后返回一个流，从而生成单个元素流。
    *   这个方法后面是 `findFirst()` 方法，返回第一个元素，实际上是原始流的最后一个元素。

以下是上述方法的实现:

**示例:**

```java
// Java program to find last
// element of a Stream in Java

import java.util.*;
import java.util.stream.*;

public class GFG {

    // Function to find the
    // last_elements in a Stream
    public static <T> T
    lastElementInStream(Stream<T> stream, int N)
    {

        T last_element
            = stream

            // This returns a stream after
            // removing first N-1 elements
            // resultant stream will contain
            // only single element
            .skip(N - 1)

            // findFirst() method return
            // the first element of
            // newly generated stream
            .findFirst()

            // if stream is empty
            // null is returned
            .orElse(null);

        return last_element;
    }

    // Driver code
    public static void main(String[] args)
    {

        Stream<String> stream
            = Stream.of("Geek_First", "Geek_2",
                        "Geek_3", "Geek_4",
                        "Geek_Last");

        int N = 5;

        // Print the last element of a Stream
        System.out.println(
            "Last Element: "
            + lastElementInStream(stream, N));
    }
}
```

**输出:**

```java
Last Element: Geek_Last
```

## 3. 查找反转流的第一个元素

**思路:**

*   获取要返回最后一个元素的元素流。
    *   要获得第一个元素，您必须首先反转流。反转可按如下方式进行:

```java
stream.sorted(Collections.reverseOrder())
```

*   这个方法后面是 `findFirst()` 方法，返回逆向流的第一个元素。
    *   因此获得了原始流的最后一个元素。

以下是上述方法的实现:

**示例:**

```java
// Java program to find last
// element of a Stream in Java

import java.util.*;
import java.util.stream.*;

public class GFG {

    // Function to find the
    // last_elements in a Stream
    public static <T> T
    lastElementInStream(Stream<T> stream)
    {
        T last_element
            = stream

            // sorted(Collections.reverseOrder())
            // is used to reverse the element of the stream
            .sorted(Collections.reverseOrder())

            // findFirst() method return
            // the first element of reversed stream
            // which is the last element of the stream
            .findFirst()

            // if stream is empty
            // null is returned
            .orElse(null);

        return last_element;
    }

    // Driver code
    public static void main(String[] args)
    {

        Stream<String> stream
            = Stream.of("Geek_First", "Geek_2",
                        "Geek_3", "Geek_4",
                        "Geek_Last");

        // Print the last element of a Stream
        System.out.println(
            "Last Element: "
            + lastElementInStream(stream));
    }
}
```

**输出:**

```java
Last Element: Geek_Last
```