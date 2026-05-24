# 如何在 Java 中找到一个流中的重复元素

> 原文: [https://www.geeksforgeeks.org/how-to-find-duplicate-elements-in-a-stream-in-java/](https://www.geeksforgeeks.org/how-to-find-duplicate-elements-in-a-stream-in-java/)

给定一个包含一些元素的`流`，任务是在 Java 中找到这个[流中的重复元素。](https://www.geeksforgeeks.org/stream-in-java/)

## 示例:

> **输入:** 流 = {5，13，4，21，13，27，2，59，59，34}
> **输出:** 【59，13】
> **解释:**
> 给定流中唯一重复的元素是 59 和 13。
>
> **输入:** 流 = {5，13，4，21，27，2，59，34}
> **输出:** 【】
> **解释:**
> 给定流中没有重复元素，因此输出为空。

在[流](https://www.geeksforgeeks.org/stream-in-java/)中查找重复元素的方法有很多:

### 1. 使用 `Set`

由于 `Set` 具有不能包含任何重复元素的特性。因此，如果我们将元素添加到 `Set` 中，它会在添加时自动丢弃重复元素。

#### 进场:

*   获取要在其中找到副本的元素流。
*   [遍历流的每个元素](https://www.geeksforgeeks.org/how-to-print-elements-of-a-stream-in-java-8/)
*   对于流中的每个元素，如果它不在集合中，则添加它。这可以使用 `Set.add()` 方法来完成。
*   如果元素已经存在于集合中，那么这个集合 `add()` 返回 `false`。
*   因此，我们可以打印这些元素或收集它们用于进一步的处理。在这种情况下，我们将打印这些元素。

下面是上述方法的实现:

#### 示例:

```java
// Java program to find the duplicate
// elements in a Stream using Set

import java.util.*;
import java.util.stream.*;

public class GfG {

    // Function to find the
    // duplicates in a Stream
    public static <T> Set<T>
    findDuplicateInStream(Stream<T> stream)
    {
        // Set to store the duplicate elements
        Set<T> items = new HashSet<>();

        // Return the set of duplicate elements
        return stream
            // Set.add() returns false
            // if the element was
            // already present in the set.
            // Hence filter such elements
            .filter(n -> !items.add(n))

            // Collect duplicate elements
            // in the set
            .collect(Collectors.toSet());
    }

    // Driver code
    public static void main(String[] args)
    {
        // Initial stream
        Stream<Integer> stream
            = Stream.of(5, 13, 4,
                        21, 13, 27,
                        2, 59, 59, 34);

        // Print the found duplicate elements
        System.out.println(
            findDuplicateInStream(stream));
    }
}
```

#### 输出:

```java
[59, 13]
```

### 2. 使用 `Collectors.groupingBy()`

`Collectors` 类中的 `groupingBy()` 方法根据某些属性对对象进行分组。因此，我们将传递冗余属性并将结果收集到一个 `Set` 中。

#### 进场:

*   获取要在其中找到副本的元素流。
*   [遍历流的每个元素](https://www.geeksforgeeks.org/how-to-print-elements-of-a-stream-in-java-8/)
*   对于流中的每个元素，使用 `Collectors.groupingBy()` 方法，将它们与它们在地图中的频率分组。
*   然后对于收集到的地图中的每个元素，如果任何元素的频率超过一个，那么这个元素就是重复的元素。
*   因此，我们可以打印这些元素或收集它们用于进一步的处理。在这种情况下，我们将打印这些元素。

下面是上述方法的实现:

#### 示例:

```java
// Java program to find the duplicate
// elements in a Stream using Collectors.groupingBy()

import java.util.*;
import java.util.stream.*;
import java.util.function.Function;

public class GfG {

    // Function to find the
    // duplicates in a Stream
    public static <T> Set<T>
    findDuplicateInStream(Stream<T> stream)
    {
        // Return the set of duplicate elements
        return stream
            // Group the elements along
            // with their frequency in a map
            .collect(
                Collectors.groupingBy(
                    Function.identity(),
                    Collectors.counting()))

            // Convert this map into a stream
            .entrySet()
            .stream()

            // Check if frequency > 1
            // for duplicate elements
            .filter(m -> m.getValue() > 1)

            // Find such elements
            .map(Map.Entry::getKey)

            // And Collect them in a Set
            .collect(Collectors.toSet());
    }

    // Driver code
    public static void main(String[] args)
    {
        // Initial stream
        Stream<Integer> stream
            = Stream.of(5, 13, 4,
                        21, 13, 27,
                        2, 59, 59, 34);

        // Print the found duplicate elements
        System.out.println(
            findDuplicateInStream(stream));
    }
}
```

#### 输出:

```java
[59, 13]
```

### 3. 使用 `Collections.frequency()`

`Collections` 类中的 `frequency()` 方法计算给定列表中指定元素的频率。然后，我们将找出频率大于 1 的元素，这些就是重复元素。

#### 进场:

*   获取要在其中找到副本的元素流。
*   [遍历流的每个元素](https://www.geeksforgeeks.org/how-to-print-elements-of-a-stream-in-java-8/)
*   对于流中的每个元素，使用 `Collections.frequency()` 方法计算每个元素的频率。
*   然后对于集合列表中的每个元素，如果任何元素的频率超过一个，那么这个元素就是一个重复的元素。
*   因此，我们可以打印这些元素或收集它们用于进一步的处理。在这种情况下，我们将打印这些元素。

下面是上述方法的实现:

#### 示例:

```java
// Java program to find the duplicate
// elements in a Stream
// using Collections.frequency()

import java.util.*;
import java.util.stream.*;

public class GfG {

    // Function to find the
    // duplicates in a Stream
    public static <T> Set<T>
    findDuplicateInStream(List<T> list)
    {
        // Return the set of duplicate elements
        return
            // Get the stream from the list
            list.stream()

                // Count the frequency of each element
                // and filter the elements
                // with frequency > 1
                .filter(i -> Collections.frequency(list, i) > 1)

                // And Collect them in a Set
                .collect(Collectors.toSet());
    }

    // Driver code
    public static void main(String[] args)
    {
        // Initial stream
        List<Integer> list
            = Arrays.asList(5, 13, 4,
                            21, 13, 27,
                            2, 59, 59, 34);

        // Print the found duplicate elements
        System.out.println(
            findDuplicateInStream(list));
    }
}
```

#### 输出:

```java
[59, 13]
```