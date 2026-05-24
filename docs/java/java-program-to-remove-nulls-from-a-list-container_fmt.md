# 从列表容器中删除空值的 Java 程序

> 原文: [https://www.geeksforgeeks.org/java-program-to-remove-nulls-from-a-list-container/](https://www.geeksforgeeks.org/java-program-to-remove-nulls-from-a-list-container/)

[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)是对象的有序集合，允许按照插入顺序存储重复值或**空值**。因此，在许多情况下移除空值非常重要。

## 示例:

```java
Input:  [Geeks, null, forGeeks, null, A computer portal]
Output: [Geeks, forGeeks, A computer portal]

Input:  [1, null, 2, 3, null, 4]
Output: [1, 2, 3, 4]
```

## 以下是在 Java 中从列表中移除空值的方法:

### 1. 使用 `List.remove()`

`List` 接口提供了一个预定义的方法 `remove(element)`，用于从列表中移除传入元素的单个出现（如果找到）。

**算法**:

1.  获取具有空值的列表。
2.  重复调用列表中的 `remove(null)`，直到所有空值都被移除。
3.  返回/打印列表（现在删除所有空值）。

```java
// Java Program to remove nulls
// from a List using List.remove()

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Create the list with null values
        List<String> list = new ArrayList<>(
            Arrays.asList("Geeks",
                          null,
                          "forGeeks",
                          null,
                          "A computer portal"));

        // Print the list
        System.out.println("Initial List: " + list);

        // Removing nulls using List.remove()
        // Repeatedly call remove() till all null are removed
        while (list.remove(null)) {
        }

        // Print the list
        System.out.println("Modified List: " + list);
    }
}
```

**Output:**

```java
Initial List: [Geeks, null, forGeeks, null, A computer portal]
Modified List: [Geeks, forGeeks, A computer portal]
```

### 2. 使用 `List.removeAll()`

`List` 接口提供了另一个预定义的方法 `removeAll(Collection)`，用于从列表中移除传入集合中所有元素的出现（如果找到）。

**算法**:

1.  获取具有空值的列表。
2.  使用 `Collections.singletonList(null)` 创建一个只包含空元素的集合。
3.  调用列表中的 `removeAll(collection)` 一次。
4.  返回/打印列表（现在删除所有空值）。

```java
// Java Program to remove nulls
// from a List using List.removeAll()

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Create the list with null values
        List<String> list = new ArrayList<>(
            Arrays.asList("Geeks",
                          null,
                          "forGeeks",
                          null,
                          "A computer portal"));

        // Print the list
        System.out.println("Initial List: " + list);

        // Removing nulls using List.removeAll()
        // passing a collection with single element "null"
        list.removeAll(Collections.singletonList(null));

        // Print the list
        System.out.println("Modified List: " + list);
    }
}
```

**Output:**

```java
Initial List: [Geeks, null, forGeeks, null, A computer portal]
Modified List: [Geeks, forGeeks, A computer portal]
```

### 3. 使用迭代器

[迭代器](https://www.geeksforgeeks.org/how-to-use-iterator-in-java/)是属于集合框架的一个接口。它允许用户遍历集合、访问数据元素并移除集合的数据元素。

**算法**:

1.  获取具有空值的列表。
2.  从列表中创建迭代器。
3.  使用创建的迭代器遍历列表的每个元素。
4.  检查每个元素是否为空。如果发现为空，对该元素调用 `Iterator.remove()`。
5.  返回/打印列表（现在删除所有空值）。

**程序:**

```java
// Java Program to remove nulls
// from a List using iterator

import java.util.*;

class GFG {

    // Generic function to remove Null Using Iterator
    public static <T> List<T> removeNullUsingIterator(List<T> list)
    {
        // Create an iterator from the list
        Iterator<T> itr = list.iterator();

        // Find and remove all null
        while (itr.hasNext()) {
            if (itr.next() == null)
                itr.remove(); // remove nulls
        }

        // Return the null
        return list;
    }

    public static void main(String[] args)
    {
```

4.  **使用 Guava Iterables removeIf()**: Guava Iterables 类提供了 `Iterables.removeIf(Iterable, Predicate)` 方法，它会从指定的 `Iterable`（或实现了 `Iterable` 的集合）中移除所有满足给定[谓词条件](https://www.geeksforgeeks.org/java-8-predicate-with-examples/)的元素。

**算法**:

1.  获取具有空值的列表。
2.  获取谓词条件 `Predicates.isNull()` 以传入 `removeIf()` 的参数。
3.  调用 `Iterables.removeIf(list, Predicates.isNull())`，其中 `list` 是带有空值的原始列表，`Predicates.isNull()` 是谓词实例。
4.  返回/打印列表（现在已删除所有空值）。

```java
// Java Program to remove nulls
// from a List using Guava Iterables

import com.google.common.base.Predicates;
import com.google.common.collect.Iterables;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Create the list with null values
        List<String> list = new ArrayList<>(
            Arrays.asList("Geeks",
                          null,
                          "forGeeks",
                          null,
                          "A computer portal"));

        // Print the list
        System.out.println("Initial List: " + list);

        // Removing nulls using Guava Iterables
        // using Predicate condition isNull()
        Iterables.removeIf(list, Predicates.isNull());

        // Print the list
        System.out.println("Modified List: " + list);
    }
}
```

**输出:**

```java
Initial List: [Geeks, null, forGeeks, null, A computer portal]
Modified List: [Geeks, forGeeks, A computer portal]
```

5.  **使用 Apache Commons Collections filter()**: Apache Commons Collections 的 `CollectionUtils` 类提供了 `filter(Iterable, Predicate)` 方法，它会从指定的可迭代对象中移除所有不满足给定[谓词条件](https://www.geeksforgeeks.org/java-8-predicate-with-examples/)的元素。

**算法**:

1.  获取具有空值的列表。
2.  获取谓词条件 `PredicateUtils.notNullPredicate()` 以传入 `filter()` 的参数，这样通过条件 `NotNull` 的元素将保留在列表中，而所有其他元素都将被过滤。
3.  调用 `CollectionUtils.filter(list, PredicateUtils.notNullPredicate())`，其中 `list` 是带有空值的原始列表，`PredicateUtils.notNullPredicate()` 实例是谓词。
4.  返回/打印列表（现在已删除所有空值）。

**程序:**

```java
// Java Program to remove nulls
// from a List using Apache Common Collection Filter()
import org.apache.commons.collections4.CollectionUtils;
import org.apache.commons.collections4.PredicateUtils;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Create the list with null values
        List<String> list = new ArrayList<>(
            Arrays.asList("Geeks",
                          null,
                          "forGeeks",
                          null,
                          "A computer portal"));

        // Print the list
        System.out.println("Initial List: " + list);

        // Removing nulls using Apache Common filter()
        // using Predicate condition notNullPredicate()
        CollectionUtils.filter(list, PredicateUtils.notNullPredicate());

        // Print the list
        System.out.println("Modified List: " + list);
    }
}
```

**输出:**

```java
Initial List: [Geeks, null, forGeeks, null, A computer portal]
Modified List: [Geeks, forGeeks, A computer portal]
```

6.  **使用 Lambdas (Java 8)**: `Stream.filter()` 方法可以在 Java 8 中使用，它返回一个由满足给定谓词条件的元素组成的流。

**算法**:

1.  获取具有空值的列表。
2.  使用 `list.stream()` 从列表中创建一个流。
3.  使用 `list.filter(x -> x != null)` 过滤不为空的元素流。
4.  使用 `collect(Collectors.toList())` 将流作为列表收集回来。
5.  返回/打印列表（现在已删除所有空值）。

```java
// Java Program to remove nulls
// from a List using Java 8 Streams

import java.util.stream.Collectors;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Create the list with null values
        List<String> list = new ArrayList<>(
            Arrays.asList("Geeks",
                          null,
                          "forGeeks",
                          null,
                          "A computer portal"));

        // Print the list
        System.out.println("Initial List: " + list);

        // Removing nulls using Java Stream
        // using Predicate condition in lambda expression
        list = list.stream()
                   .filter(x -> x != null)
                   .collect(Collectors.toList());

        // Print the list
        System.out.println("Modified List: " + list);
    }
}
```

**输出:**

```java
Initial List: [Geeks, null, forGeeks, null, A computer portal]
Modified List: [Geeks, forGeeks, A computer portal]
```