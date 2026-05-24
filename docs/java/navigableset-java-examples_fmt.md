# Java NavigableSet 示例

> 原文: [https://www.geeksforgeeks.org/navigableset-java-examples/](https://www.geeksforgeeks.org/navigableset-java-examples/)

`NavigableSet` 表示 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)中的一个可导航集合。`NavigableSet` 接口继承自 [`SortedSet`](https://www.geeksforgeeks.org/sortedset-java-examples/) 接口。它的行为类似于排序集，除了排序集的排序机制之外，我们还有可用的导航方法。
例如，`NavigableSet` 接口可以以与 `SortedSet` 中定义的顺序相反的顺序导航集合。可以按升序或降序访问和遍历 `NavigableSet`。实现这个接口的类有 [`TreeSet`](https://www.geeksforgeeks.org/treeset-in-java/) 和 [`ConcurrentSkipListSet`](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentSkipListSet.html)。

![NavigableSet in Java with Examples](img/fe0ed9520fa852c7d04e9ee3455bc168.png)

这里，`E` 是这个集合维护的元素类型。

**所有超接口:**

`Collection<E>`, `Iterable<E>`, [`Set<E>`](https://www.geeksforgeeks.org/set-in-java/), [`SortedSet<E>`](https://www.geeksforgeeks.org/sortedset-java-examples/)

**所有已知的实现类:**

[`ConcurrentSkipListSet`](https://www.geeksforgeeks.org/concurrentskiplistset-in-java-with-examples/), [`TreeSet`](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)

**声明:** `NavigableSet` 声明为

```java
public interface NavigableSet<E> extends SortedSet<E>
```

**创建 NavigableSet 对象**

由于 `NavigableSet` 是一个接口，因此不能创建 `NavigableSet` 类型的对象。我们总是需要一个实现这个接口的类来创建一个对象。此外，在 Java 1.5 中引入泛型后，可以限制 `NavigableSet` 中可以存储的对象类型。这种类型安全集合可以定义为:

```java
// Obj 是要存储在 NavigableSet 中的对象的类型
NavigableSet<Obj> set = new TreeSet<Obj>();
```

**示例:**

## Java 语言示例

```java
// Java program to demonstrate
// the working of NavigableSet
import java.util.NavigableSet;
import java.util.TreeSet;

public class NavigableSetDemo
{
    public static void main(String[] args)
    {
        NavigableSet<Integer> ns = new TreeSet<>();
        ns.add(0);
        ns.add(1);
        ns.add(2);
        ns.add(3);
        ns.add(4);
        ns.add(5);
        ns.add(6);

        // Get a reverse view of the navigable set
        NavigableSet<Integer> reverseNs = ns.descendingSet();

        // Print the normal and reverse views
        System.out.println("Normal order: " + ns);
        System.out.println("Reverse order: " + reverseNs);

        NavigableSet<Integer> threeOrMore = ns.tailSet(3, true);
        System.out.println("3 or  more:  " + threeOrMore);
        System.out.println("lower(3): " + ns.lower(3));
        System.out.println("floor(3): " + ns.floor(3));
        System.out.println("higher(3): " + ns.higher(3));
        System.out.println("ceiling(3): " + ns.ceiling(3));

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("Navigable Set:  " + ns);

        System.out.println("pollLast(): " + ns.pollLast());
        System.out.println("Navigable Set:  " + ns);

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("Navigable Set:  " + ns);

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("Navigable Set:  " + ns);

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("Navigable Set:  " + ns);

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("pollLast(): " + ns.pollLast());
    }
}
```

**输出**

```java
Normal order: [0, 1, 2, 3, 4, 5, 6]
Reverse order: [6, 5, 4, 3, 2, 1, 0]
3 or  more:  [3, 4, 5, 6]
lower(3): 2
floor(3): 3
higher(3): 4
ceiling(3): 3
pollFirst(): 0
Navigable Set:  [1, 2, 3, 4, 5, 6]
pollLast(): 6
Navigable Set:  [1, 2, 3, 4, 5]
pollFirst(): 1
Navigable Set:  [2, 3, 4, 5]
pollFirst(): 2
Navigable Set:  [3, 4, 5]
pollFirst(): 3
Navigable Set:  [4, 5]
pollFirst(): 4
pollLast(): 5
```

### 在 NavigableSet 上执行各种操作

由于 `NavigableSet` 是一个接口，因此它只能与实现该接口的类一起使用。`TreeSet` 是实现 `NavigableSet` 接口的类。现在，让我们看看如何在 `TreeSet` 上执行一些常用的操作。

**1. 添加元素:** 为了给 `NavigableSet` 添加一个元素，我们可以使用 [`add()`](https://www.geeksforgeeks.org/navigableset-add-method-in-java/?ref=rp) 方法。但是，插入顺序不会保留在 `TreeSet` 中。在内部，对于每个元素，值都是按升序进行比较和排序的。我们需要注意，重复的元素是不允许的，所有重复的元素都会被忽略。此外，`NavigableSet` 不接受空值。

## Java 语言示例

```java
// Java code to demonstrate
// adding of elements in
// NavigableSet
import java.util.*;
import java.io.*;

class NavigableSetDemo {

    public static void main(String[] args)
    {
        NavigableSet<String> ts = new TreeSet<String>();

        // Elements are added using add() method
        ts.add("A");
        ts.add("B");
        ts.add("C");
        ts.add("A");

        System.out.println(ts);
    }
}
```

**输出:**

```java
[A, B, C]
```

**2. 访问元素:** 添加元素后，如果我们希望访问元素，我们可以使用内置方法，如 `contains()`, `first()`, `last()` 等。

*   [`contains()`](https://www.geeksforgeeks.org/sortedset-contains-method-in-java-with-examples/)
*   [`first()`](https://www.geeksforgeeks.org/sortedset-first-method-in-java/)
*   [`last()`](https://www.geeksforgeeks.org/sortedset-last-method-in-java/)

## Java 语言示例

```java
// Java program to access
// the elements of NavigableSet
import java.util.*;
import java.io.*;

class NavigableSetDemo {

    public static void main(String[] args)
    {
        NavigableSet<String> ts = new TreeSet<String>();

        // Elements are added using add() method
        ts.add("A");
        ts.add("B");
        ts.add("C");
        ts.add("A");

        System.out.println("Navigable Set is " + ts);

        String check = "D";

        // Check if the above string exists in
        // the NavigableSet or not
        System.out.println("Contains " + check + " "
                           + ts.contains(check));

        // Print the first element in
        // the NavigableSet
        System.out.println("First Value " + ts.first());

        // Print the last element in
        // the NavigableSet
        System.out.println("Last Value " + ts.last());
    }
}
```

**输出:**

```java
Navigable Set is [A, B, C]
Contains D false
First Value A
Last Value C
```

**3. 移除值:** 可以使用 `remove()`, `pollFirst()`, `pollLast()` 方法从 `NavigableSet` 中移除值。

*   [`remove()`](https://www.geeksforgeeks.org/sortedset-remove-method-in-java-with-examples/)
*   [`pollFirst()`](https://www.geeksforgeeks.org/navigableset-pollfirst-method-in-java/?ref=rp)
*   [`pollLast()`](https://www.geeksforgeeks.org/navigableset-polllast-method-in-java/?ref=rp)

## Java 语言示例

```java
// Java Program to remove the
// elements from NavigableSet
import java.util.*;
import java.io.*;

class NavigableSetDemo {

    public static void main(String[] args)
    {
        NavigableSet<String> ts = new TreeSet<String>();

        // Elements are added using add() method
        ts.add("A");
        ts.add("B");
        ts.add("C");
        ts.add("B");
        ts.add("D");
        ts.add("E");

        System.out.println("Initial TreeSet " + ts);

        // Removing the element b
        ts.remove("B");

        System.out.println("After removing element " + ts);

        // Remove the First element of TreeSet
        ts.pollFirst();

        System.out.println(
            "After the removal of First Element " + ts);

        // Remove the Last element of TreeSet
        ts.pollLast();

        System.out.println(
            "After the removal of Last Element " + ts);
    }
}
```

**输出:**

```java
Initial TreeSet [A, B, C, D, E]
After removing element [A, C, D, E]
After the removal of First Element [C, D, E]
After the removal of Last Element [C, D]
```

**4. 遍历 NavigableSet:** 有多种方法可以遍历 `NavigableSet`。最著名的一个是使用[增强 for 循环](https://www.geeksforgeeks.org/loops-in-java/)。

## Java 语言示例

```java
// Java program to iterate
// through NavigableSet

import java.util.*;
import java.io.*;

class NavigableSetDemo {

    public static void main(String[] args)
    {
        NavigableSet<String> ts = new TreeSet<String>();

        // Elements are added using add() method
        ts.add("C");
        ts.add("D");
        ts.add("E");
        ts.add("A");
        ts.add("B");
        ts.add("Z");

        // Iterating though the NavigableSet
        for (String value : ts)
            System.out.print(value + ", ");
        System.out.println();
    }
}
```

**输出:**

```java
A, B, C, D, E, Z,
```

### 导航集的方法

以下是 `NavigableSet` 界面中的方法。

| 方法 | 描述 |
| --- | --- |
| `ceiling(E e)` | 返回集合中大于或等于给定元素的最小元素，如果没有这样的元素，则返回 `null`。 |
| `descendingIterator()` | 返回此集合中元素的降序迭代器。 |
| `descendingSet()` | 返回此集合中元素的逆序视图。 |
| `floor(E e)` | 返回集合中小于或等于给定元素的最大元素，如果没有这样的元素，则返回 `null`。 |
| `headSet(E toElement)` | 返回此集合中元素严格小于 `toElement` 的部分的视图。 |
| `headSet(E toElement, boolean inclusive)` | 返回此集合中元素小于（如果 `inclusive` 为 `true`，则小于或等于）`toElement` 的部分的视图。 |
| `higher(E e)` | 返回集合中严格大于给定元素的最小元素，如果没有这样的元素，则返回 `null`。 |
| `iterator()` | 返回此集合中元素的升序迭代器。 |
| `lower(E e)` | 返回集合中严格小于给定元素的最大元素，如果没有这样的元素，则返回 `null`。 |
| `pollFirst()` | 检索并移除第一个（最低）元素，如果集合为空，则返回 `null`。 |
| `pollLast()` | 检索并删除最后一个（最高）元素，如果集合为空，则返回 `null`。 |
| `subSet(E fromElement, boolean fromInclusive, E toElement, boolean toInclusive)` | 返回此集合中元素范围从 `fromElement` 到 `toElement` 的部分的视图。 |
| `subSet(E fromElement, E toElement)` | 返回此集合中元素范围从 `fromElement` 到 `toElement` 的部分的视图。 |
| `tailSet(E fromElement)` | 返回此集合中元素大于或等于 `fromElement` 的部分的视图。 |
| `tailSet(E fromElement, boolean inclusive)` | 返回此集合中元素大于（如果 `inclusive` 为 `true`，则大于或等于）`fromElement` 的部分的视图。 |

### 从接口 `java.util.SortedSet` 继承的方法

| 方法 | 描述 |
| --- | --- |
| `comparator()` | 返回用于对此集合中的元素进行排序的比较器，如果该集合使用其元素的自然排序，则返回 `null`。 |
| `first()` | 返回此集合中的第一个（最低）元素。 |
| `last()` | 返回此集合中最后一个（最高）的元素。 |
| `spliterator()` | 在此有序集合的元素上创建 `Spliterator`。 |

### 从接口 `java.util.Set` 继承的方法

| 方法 | 描述 |
| --- | --- |
| `add(E e)` | 用于向集合中添加特定元素。只有当集合中没有指定元素时，才会添加元素；否则，如果集合中已经有该元素，函数将返回 `false`。 |
| `addAll(Collection<? extends E> c)` | 用于将参数集合中的所有元素追加到现有集合中。元素是随机添加的，没有遵循任何特定的顺序。 |
| `clear()` | 用于从集合中移除所有元素，但不删除集合本身。集合的引用仍然存在。 |
| `contains(Object o)` | 用于检查集合中是否存在特定元素。 |
| `containsAll(Collection<?> c)` | 用于检查集合是否包含给定集合中存在的所有元素。如果集合包含所有元素，则此方法返回 `true`；如果缺少任何元素，则返回 `false`。 |
| `equals(Object o)` | 将指定的对象与此集合进行比较以判断相等性。 |
| `hashCode()` | 返回此集合实例的哈希码值。 |
| `isEmpty()` | 用于检查此集合是否为空。 |
| `remove(Object o)` | 用于从集合中移除给定的元素。如果集合中存在指定的元素，此方法返回 `true`，否则返回 `false`。 |
| `removeAll(Collection<?> c)` | 用于从此集合中移除也包含在参数集合中的所有元素。如果此集合因调用而改变，则此方法返回 `true`。 |
| `retainAll(Collection<?> c)` | 用于仅保留此集合中也包含在参数集合中的所有元素。如果此集合因调用而改变，则此方法返回 `true`。 |
| `size()` | 返回此集合中的元素数量。 |
| `toArray()` | 返回包含此集合中所有元素的数组。 |
| `toArray(T[] a)` | 返回包含此集合中所有元素的数组；返回数组的运行时类型是指定数组的运行时类型。 |

### 在接口 `java.util.Collection` 中声明的方法

| 方法 | 描述 |
| --- | --- |
| `parallelStream()` | 以此集合为源返回一个可能并行的流。 |
| `removeIf(Predicate<? super E> filter)` | 移除此集合中满足给定谓词的所有元素。 |
| `stream()` | 返回以此集合为源的顺序流。 |
| `toArray(IntFunction<T[]> generator)` | 使用提供的生成器函数分配返回的数组，返回包含此集合中所有元素的数组。 |

### 在接口 `java.lang.Iterable` 中声明的方法

| 方法 | 描述 |
| --- | --- |
| `forEach(Consumer<? super T> action)` | 对 `Iterable` 的每个元素执行给定的操作，直到所有元素都被处理完或者该操作引发异常。 |

本文由 **Pratik Agarwal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。