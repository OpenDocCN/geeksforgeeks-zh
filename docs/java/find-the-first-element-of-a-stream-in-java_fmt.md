# 在 Java 中找到一个流的第一个元素

> 原文：[https://www.geeksforgeeks.org/find-the-first-element-of-a-stream-in-java/](https://www.geeksforgeeks.org/find-the-first-element-of-a-stream-in-java/)

给定一个包含一些元素的`流`，任务是在 Java 中获取[流的第一个元素。](https://www.geeksforgeeks.org/stream-in-java/)

**示例：**

> **输入：**流 = {“Geek_First”, “Geek_2”, “Geek_3”, “Geek_4”, “Geek_Last”}
> **输出：**Geek_First
>
> **输入：**流 = {1, 2, 3, 4, 5, 6, 7}
> **输出：**1

有许多方法可以找到[流](https://www.geeksforgeeks.org/stream-in-java/)中的第一个元素：

1.  **使用 `Stream.reduce()` 方法：** `reduce` 方法对流中的两个元素进行操作，并根据所需条件返回元素。因此，此方法可用于缩减流，使其仅包含第一个元素。

**思路：**

*   获取要返回第一个元素的元素流。
    *   要获得第一个元素，可以使用 `reduce()` 方法忽略第二个元素，重复操作，直到没有第二个元素。

```java
stream.reduce((first, second) -> first)
```

*   这将流中的一组元素减少为单个元素，即*第一个*。
    *   因此，流中将只保留唯一的单个元素，即第一个元素。

以下是上述方法的实现：

**示例：**

```java
// Java program to find first
// element of a Stream in Java

import java.util.*;
import java.util.stream.*;

public class GFG {

    // Function to find the
    // first element in a Stream
    public static <T> T
    firstElementInStream(Stream<T> stream)
    {
        T first_element
            = stream

                // reduce() method reduces the Stream
                // to a single element, which is first.
                .reduce((first, second) -> first)

                // if stream is empty
                // null is returned
                .orElse(null);

        return first_element;
    }

    // Driver code
    public static void main(String[] args)
    {

        Stream<String> stream
            = Stream.of("Geek_First", "Geek_2",
                        "Geek_3", "Geek_4",
                        "Geek_Last");

        // Print the first element of a Stream
        System.out.println(
            "First Element: "
            + firstElementInStream(stream));
    }
}
```

**输出：**

```java
First Element: Geek_First
```

2.  **使用 `Stream.findFirst()` 方法：** `findFirst()` 方法将返回流的第一个元素，如果流为空则返回一个空值。

**思路：**

*   获取要返回第一个元素的元素流。
    *   要获取第一个元素，可以直接使用 `findFirst()` 方法。

```java
stream.findFirst()
```

*   这将返回流的第一个元素。

以下是上述方法的实现：

**示例：**

```java
// Java program to find first
// element of a Stream in Java

import java.util.*;
import java.util.stream.*;

public class GFG {

    // Function to find the
    // first element in a Stream
    public static <T> T
    firstElementInStream(Stream<T> stream)
    {
        T first_element
            = stream

                // findFirst() method returns
                // the first element of stream
                .findFirst()

                // if stream is empty
                // null is returned
                .orElse(null);

        return first_element;
    }

    // Driver code
    public static void main(String[] args)
    {

        Stream<String> stream
            = Stream.of("Geek_First", "Geek_2",
                        "Geek_3", "Geek_4",
                        "Geek_Last");

        // Print the first element of a Stream
        System.out.println(
            "First Element: "
            + firstElementInStream(stream));
    }
}
```

**输出：**

```java
First Element: Geek_First
```