# Java 中的集合与集合示例

> 原文：[`https://www.geeksforgeeks.org/collection-vs-collections-in-java-with-example/`](https://www.geeksforgeeks.org/collection-vs-collections-in-java-with-example/)

## Collection

`Collection` 是 `java.util` 包中存在的一个[接口](https://www.geeksforgeeks.org/interfaces-in-java/)，用于将一组单独的对象表示为一个单元。它类似于 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 语言中的容器。集合被认为是集合框架的根接口。它提供了几个类和接口来将一组单独的对象表示为一个单元。

[`List`](https://www.geeksforgeeks.org/list-interface-java-examples/)、[`Set`](https://www.geeksforgeeks.org/set-in-java/)、[`Queue`](https://www.geeksforgeeks.org/queue-interface-java/) 是 `Collection` 接口的主要子接口。`Map` 接口也是 Java 集合框架的一部分，但是它不继承 `Collection` 接口。`add()`、`remove()`、`clear()`、`size()`、`contains()` 是 `Collection` 接口的重要方法。

**声明：**

```java
public interface Collection<E> extends Iterable<E>

Type Parameters: E - the type of elements returned by this iterator
```

## Collections

`Collections` 是 `java.util` 包中存在的一个实用类，它定义了排序和搜索等多种实用方法，用于对 `Collection` 进行操作。它包含所有静态方法。这些方法为开发人员提供了急需的便利，允许他们有效地使用[集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)。例如，它有一个方法 `sort()` 按照默认的排序顺序对集合元素进行排序，它有一个方法 `min()` 和 `max()` 分别找出集合元素中的最小值和最大值。

**声明：**

```java
public class Collections extends Object
```

## Collection vs Collections

| **Collection** | **Collections** |
| --- | --- |
| 它是一个接口。 | 它是一个工具类。 |
| 它用于将一组单独的对象表示为一个单元。 | 它定义了多种用于操作集合的实用方法。 |
| `Collection` 是一个接口，自 Java 8 起包含静态方法。接口也可以包含抽象方法和默认方法。 | 它只包含静态方法。 |

## Java 语言示例

```java
// Java program to demonstrate the difference
// between Collection and Collections

import java.io.*;
import java.util.*;

class GFG {

    public static void main (String[] args)
    {
        // Creating an object of List<String>
        List<String> arrlist = new ArrayList<String>();

        // Adding elements to arrlist
        arrlist.add("geeks");
        arrlist.add("for");
        arrlist.add("geeks");

        // Printing the elements of arrlist
        // before operations
        System.out.println("Elements of arrlist before the operations:");
        System.out.println(arrlist);

        System.out.println("Elements of arrlist after the operations:");

        // Adding all the specified elements
        // to the specified collection
        Collections.addAll(arrlist, "web", "site");

        // Printing the arrlist after
        // performing addAll() method
        System.out.println(arrlist);

        // Sorting all the elements of the
        // specified collection according to
        // default sorting order
        Collections.sort(arrlist);

        // Printing the arrlist after
        // performing sort() method
        System.out.println(arrlist);
    }
}
```

**输出**

```java
Elements of arrlist before the operations:
[geeks, for, geeks]
Elements of arrlist after the operations:
[geeks, for, geeks, web, site]
[for, geeks, geeks, site, web]
```