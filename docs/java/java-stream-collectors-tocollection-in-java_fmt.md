# Java 流 | Collectors toCollection() 在 Java 中

> 原文: [https://www.geeksforgeks.org/java-stream-collectors-tocollection-in-java/](https://www.geeksforgeks.org/java-stream-collectors-tocollection-in-java/)

## `toCollection(Supplier<C> collectionFactory)`

`toCollection(Supplier<C> collectionFactory)` 方法用于使用 `Collector` 创建集合。它返回一个收集器，该收集器按照输入元素传递的顺序将输入元素累积到一个新的集合中。

### 语法:

```java
public static <T, C extends Collection<T>> Collector<T, ?, C>
      toCollection(Supplier<C> collectionFactory)
```

其中：

*   `Collection`：集合层次中的根接口。集合表示一组对象，称为其元素。一些集合允许重复的元素，而另一些则不允许。有些是有序的，有些是无序的。
*   `Collector<T, A, R>`：一种将输入元素累加到一个可变结果容器中的可变约简操作，在所有输入元素都被处理后，可选地将累加的结果转换为最终表示。还原操作可以顺序执行，也可以并行执行。
    *   `T`：归约运算的输入元素类型。
    *   `A`：还原操作的可变累加类型。
    *   `R`：归约运算的结果类型。
*   `Supplier`：功能接口，因此可以用作 lambda 表达式或方法引用的赋值目标。
*   `collectionFactory`：返回适当类型的新的空集合的 `Supplier`。

### 参数:

该方法采用类型为 `Supplier<C>` 的强制参数 `collectionFactory`，该参数返回适当类型的新的空集合。

### 返回值:

该方法返回一个收集器，该收集器按照相遇顺序将所有输入元素收集到一个集合中。

下面给出了一些例子来更好地说明 `toCollection()` 的实现:

### 例 1:

```java
// Java code to demonstrate Collectors
// toCollection(Supplier collectionFactory) method

import java.util.*;
import java.util.stream.Collectors;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a string stream
        Stream<String> s = Stream.of("Geeks", "for", "GeeksClasses");

        // Using toCollection() method
        // to create a collection
        Collection<String> names = s
                                       .collect(Collectors
                                                    .toCollection(TreeSet::new));

        // Printing the elements
        System.out.println(names);
    }
}
```

**Output:**

```java
[Geeks, GeeksClasses, for]
```

### 例 2:

```java
// Java code to demonstrate Collectors
// toCollection(Supplier collectionFactory) method

import java.util.Collection;
import java.util.TreeSet;
import java.util.stream.Collectors;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a string stream
        Stream<String> s = Stream.of("2.5", "6", "4");

        // Using Collectors toCollection()
        Collection<String> names = s
                                       .collect(Collectors
                                                    .toCollection(TreeSet::new));

        // Printing the elements
        System.out.println(names);
    }
}
```

**Output:**

```java
[2.5, 4, 6]
```