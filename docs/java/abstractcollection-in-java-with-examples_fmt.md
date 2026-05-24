# Java 抽象集合，带示例

> 原文：`https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/`

Java 中的 `AbstractCollection` 类是 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的一部分，实现了 `Collection` 接口。它用于实现一个不可修改的集合，对于这个集合，只需要扩展这个抽象集合类，并且只实现迭代器和大小方法。

## 类层次结构

```java
java.lang.Object
 ↳ java.util
    ↳ Class AbstractCollection<E>
```

## 语法

```java
public abstract class AbstractCollection<E>
    extends Object
       implements Collection<E>

where E is the type of elements maintained
by this collection.
```

## 构造函数

*   `protected AbstractCollection()`：默认的构造函数，但是受到保护，不允许创建 abstract collection 对象。

下面是用 Java 举例说明 `AbstractCollection` 的示例程序：

```java
// Java code to illustrate AbstractCollection

import java.util.*;
import java.util.AbstractCollection;

public class GFG {
    public static void main(String[] args)
    {
        // Create an empty collection
        AbstractCollection<Object>
            abs = new ArrayList<Object>();

        // Use add() method to add
        // elements in the collection
        abs.add("Welcome");
        abs.add("To");
        abs.add("Geeks");
        abs.add("4");
        abs.add("Geeks");

        // Displaying the Collection
        System.out.println("AbstractCollection: "
                           + abs);
    }
}
```

**输出：**

```java
AbstractCollection: [Welcome, To, Geeks, 4, Geeks]
```

## 方法

1.  `add(E e)`：此方法确保此集合包含指定的元素（可选操作）。
2.  `addAll(Collection<? extends E> c)`：此方法将指定集合中的所有元素添加到此集合（可选操作）。
3.  `clear()`：此方法从此集合中移除所有元素（可选操作）。
4.  `contains(Object o)`：如果此集合包含指定的元素，则返回 `true`。
5.  `containsAll(Collection<?> c)`：如果此集合包含指定集合中的所有元素，则返回 `true`。
6.  `isEmpty()`：如果此集合不包含任何元素，则返回 `true`。
7.  `iterator()`：返回此集合中元素的迭代器。
8.  `remove(Object o)`：从此集合中移除指定元素的单个实例（如果存在）（可选操作）。
9.  `size()`：返回此集合中的元素数。
10. `toArray()`：返回一个包含此集合中所有元素的数组。
11. `<T> T[] toArray(T[] a)`：返回一个包含此集合中所有元素的数组；返回数组的运行时类型是指定数组的运行时类型。
12. `toString()`：返回此集合的字符串表示形式。

## 示例

```java
// Java code to illustrate
// methods of AbstractCollection

import java.util.*;
import java.util.AbstractCollection;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {
        // Creating an empty collection
        AbstractCollection<String>
            abs1 = new TreeSet<String>();

        // Use add() method to add
        // elements into the Collection
        abs1.add("Welcome");
        abs1.add("To");
        abs1.add("Geeks");
        abs1.add("4");
        abs1.add("Geeks");
        abs1.add("TreeSet");

        // Displaying the Collection
        System.out.println("AbstractCollection 1: "
                           + abs1);

        // Creating anothe Collection
        AbstractCollection<String>
            abs2 = new TreeSet<String>();

        // Displaying the Collection
        System.out.println("AbstractCollection 2: "
                           + abs2);

        // Using addAll() method to Append
        abs2.addAll(abs1);

        // Displaying the Collection
        System.out.println("AbstractCollection 2: "
                           + abs2);

        // Clearing the collection
        // using clear() method
        abs1.clear();

        // Check for the empty collection
        System.out.println("Is the collection empty? "
                           + abs1.isEmpty());
    }
}
```

**输出：**

```java
AbstractCollection 1: [4, Geeks, To, TreeSet, Welcome]
AbstractCollection 2: []
AbstractCollection 2: [4, Geeks, To, TreeSet, Welcome]
Is the collection empty? true
```

**参考：**`https://docs.oracle.com/javase/7/docs/api/java/util/AbstractCollection.html`