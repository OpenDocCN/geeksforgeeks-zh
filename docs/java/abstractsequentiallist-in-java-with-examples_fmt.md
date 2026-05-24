# Java 中的抽象顺序列表，带示例

> 原文: [https://www.geeksforgeeks.org/abstractsequentiallist-in-java-with-examples/](https://www.geeksforgeeks.org/abstractsequentiallist-in-java-with-examples/)

Java 中的 `AbstractSequentialList` 类是 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的一部分，实现了 `Collection` 接口和 `AbstractCollection` 类。它用于实现一个不可修改的列表，对于这个列表，只需要扩展这个抽象列表类，并且只实现 `get()` 和 `size()` 方法。

这个类提供了一个 `List` 接口的框架实现，以最小化实现这个接口所需的工作量，这个接口由一个“顺序访问”数据存储(如链表)支持。对于随机访问数据(如数组)，应该优先使用 `AbstractList`。

**等级:**

![AbstractSequentialList-in-Java](img/698f485605df7d437bdc8da957f576cf.png)

**声明:**

```java
public abstract class AbstractSequentialList<E>
    extends AbstractList<E>

Where E is the type of element maintained by this List.
```

实现 `Iterable<E>`、`Collection<E>`、`List<E>` 接口。`LinkedList` 是 `AbstractSequentialList` 的唯一直接子类。

**构造函数:**
*   `protected AbstractSequentialList()` – 默认构造函数，但受保护，不允许创建 `AbstractSequentialList` 对象。

```java
AbstractSequentialList<E> asl = new LinkedList<E>();
```

**示例 1:**
`AbstractSequentialList` 是一个抽象类，所以应该为它分配一个子类的实例，比如 `LinkedList`。

## Java 代码示例 1

```java
// Java code to illustrate AbstractSequentialList
import java.util.*;

public class GfG {
    public static void main(String[] args)
    {
        // Creating an instance of
        // the AbstractSequentialList
        AbstractSequentialList<Integer> absl
            = new LinkedList<>();

        // adding elements to absl
        absl.add(5);
        absl.add(6);
        absl.add(7);

        // Printing the list
        System.out.println(absl);
    }
}
```

**输出:**

```java
[5, 6, 7]
```

**例 2:**

## Java 代码示例 2

```java
// Java code to illustrate
// methods of AbstractSequentialList

import java.util.*;
import java.util.AbstractSequentialList;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractSequentialList
        AbstractSequentialList<String>
            absqlist = new LinkedList<String>();

        // Using add() method to
          // add elements in the list
        absqlist.add("Geeks");
        absqlist.add("for");
        absqlist.add("Geeks");
        absqlist.add("10");
        absqlist.add("20");

        // Output the list
        System.out.println("AbstractSequentialList: "
                           + absqlist);

        // Remove the head using remove()
        absqlist.remove(3);

        // Print the final list
        System.out.println("Final List: "
                           + absqlist);

        // Fetching the specific
          // element from the list
        // using get() method
        System.out.println("The element is: "
                           + absqlist.get(2));
    }
}
```

**输出:**

```java
AbstractSequentialList: [Geeks, for, Geeks, 10, 20]
Final List: [Geeks, for, Geeks, 20]
The element is: Geeks
```

### 抽象序列列表的方法

| 方法 | 描述 |
| --- | --- |
| `add(int index, E element)` | 在列表中的指定位置插入指定元素(可选操作)。 |
| `addAll(int index, Collection<? extends E> c)` | 将指定集合中的所有元素插入列表中的指定位置(可选操作)。 |
| `get(int index)` | 返回列表中指定位置的元素。 |
| `iterator()` | 返回列表中元素的迭代器(按正确的顺序)。 |
| `listIterator(int index)` | 返回列表中元素的列表迭代器(按正确的顺序)。 |
| `remove(int index)` | 移除列表中指定位置的元素(可选操作)。 |
| `set(int index, E element)` | 用指定的元素替换列表中指定位置的元素(可选操作)。 |

### 方法继承自 java.util.AbstractList 类

| 方法 | 描述 |
| --- | --- |
| `add(E e)` | 将指定的元素追加到该列表的末尾(可选操作)。 |
| `clear()` | 从此列表中移除所有元素(可选操作)。 |
| `equals(Object o)` | 将指定的对象与该列表进行比较，看是否相等。 |
| `hashCode()` | 返回此列表的哈希代码值。 |
| `indexOf(Object o)` | 返回此列表中指定元素的第一个匹配项的索引，如果此列表不包含该元素，则返回-1。 |
| `lastIndexOf(Object o)` | 返回此列表中指定元素最后一次出现的索引，如果此列表不包含该元素，则返回-1。 |
| `listIterator()` | 返回列表中元素的列表迭代器(按正确的顺序)。 |
| `removeRange(int fromIndex, int toIndex)` | 从该列表中删除索引介于 `fromIndex`(包含)和 `toIndex`(不包含)之间的所有元素。 |
| `subList(int fromIndex, int toIndex)` | 返回此列表中指定的 `fromIndex`(包含)和 `toIndex`(不包含)之间的部分的视图。 |

### 方法继承自 java.util.AbstractCollection 类

| 方法 | 描述 |
| --- | --- |
| `addAll(Collection<? extends E> c)` | 将指定集合中的所有元素添加到此集合中(可选操作)。 |
| `contains(Object o)` | 如果此集合包含指定的元素，则返回 `true`。 |
| `containsAll(Collection<?> c)` | 如果此集合包含指定集合中的所有元素，则返回 `true`。 |
| `isEmpty()` | 如果此集合不包含元素，则返回 `true`。 |
| `remove(Object o)` | 从该集合中移除指定元素的单个实例(如果存在)(可选操作)。 |
| `removeAll(Collection<?> c)` | 移除此集合中也包含在指定集合中的所有元素(可选操作)。 |
| `retainAll(Collection<?> c)` | 仅保留此集合中包含在指定集合中的元素(可选操作)。 |
| `toArray()` | 返回包含此集合中所有元素的数组。 |
| `toArray(T[] a)` | 返回包含此集合中所有元素的数组；返回数组的运行时类型是指定数组的运行时类型。 |
| `toString()` | 返回此集合的字符串表示形式。 |

### 从接口继承的方法

| 方法 | 描述 |
| --- | --- |
| `parallelStream()` | 以此集合为源返回一个可能并行的流。 |
| `removeIf(Predicate<? super E> filter)` | 移除此集合中满足给定谓词的所有元素。 |
| `stream()` | 返回以此集合为源的顺序流。 |
| `toArray(IntFunction<T[]> generator)` | 使用提供的生成器函数分配返回的数组，返回包含此集合中所有元素的数组。 |

### 从接口 java.lang.Iterable 继承的方法

| 方法 | 描述 |
| --- | --- |
| `forEach(Consumer<? super T> action)` | 对 `Iterable` 的每个元素执行给定的操作，直到所有元素都被处理完或者该操作引发异常。 |

### 从接口继承的方法

| 方法 | 描述 |
| --- | --- |
| `addAll(Collection<? extends E> c)` | 将指定集合中的所有元素按顺序追加到该列表的末尾由指定集合的迭代器返回(可选操作)。 |
| `contains(Object o)` | 如果此列表包含指定的元素，则返回 true。 |
| `containsAll(Collection<?> c)` | 如果此列表包含指定集合的所有元素，则返回 true。 |
| `isEmpty()` | 如果此列表不包含任何元素，则返回 true。 |
| `remove(Object o)` | 从列表中删除指定元素的第一个匹配项(如果存在)(可选操作)。 |
| `removeAll(Collection<?> c)` | 从此列表中移除指定集合中包含的所有元素(可选操作)。 |
| `replaceAll(UnaryOperator<E> operator)` | 将列表中的每个元素替换为对该元素应用运算符的结果。 |
| `retainAll(Collection<?> c)` | 仅保留此列表中包含在指定集合中的元素(可选操作)。 |
| `size()` | 返回此列表中的元素数量。 |
| `sort(Comparator<? super E> c)` | 根据指定比较器引发的顺序对该列表进行排序。 |
| `spliterator()` | 在此列表中的元素上创建拆分器。 |
| `toArray()` | 返回一个数组，该数组按正确的顺序(从第一个元素到最后一个元素)包含列表中的所有元素。 |
| `<T> T[] toArray(T[] a)` | 返回一个数组，该数组包含此列表中按正确顺序排列的所有元素(从第一个元素到最后一个元素)；返回数组的运行时类型是指定数组的运行时类型。 |

`参考`：`https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/AbstractSequentialList.html`