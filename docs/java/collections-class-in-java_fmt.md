# Java 中的集合类

> 原文: [https://www.geeksforgeeks.org/collections-class-in-java/](https://www.geeksforgeeks.org/collections-class-in-java/)

`Collections`类是 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的成员。`java.util`包是包含`Collections`类的包。`Collections`类基本上与对集合进行操作或返回集合的[静态方法](https://www.geeksforgeeks.org/static-methods-vs-instance-methods-java/)一起使用。如果传递给方法的集合或对象为空，则该类的所有方法都会抛出`NullPointerException`。

## 语法声明

```java
public class Collections
extends Object
```

> **记住:** [`Object`](https://www.geeksforgeeks.org/object-class-in-java/)是所有类的父类。

## 集合类字段

`Collections`类基本上包含下面列出的 3 个字段，可以用来返回不可变的实体。

*   获取一个不可变的空列表
*   获取不可变的空映射
*   获取一个不可变的空集合

现在让我们讨论一下这个类中存在的方法，这样我们就可以在以后的程序中实现这些内置的功能。以下是以表格形式列出的方法，如下所示:

<figure class="table">
</figure>

# Java Collections 类常用方法

## 方法列表

| 方法 | 描述 |
| --- | --- |
| `addAll(Collection<? extends E> c)` | 它用于在调用集合中插入指定的集合元素。 |
| `asLifoQueue(Deque<? extends T> deque)` | 这个方法返回一个作为后进先出队列的视图。 |
| `binarySearch(List<? extends Comparable<? super T>> list, T key)` | 此方法使用指定列表中的二分搜索法搜索密钥。 |
| `binarySearch(List<? extends T> list, T key, Comparator<? super T> c)` | 此方法使用二分搜索法算法在指定列表中搜索指定对象。 |
| `checkedCollection(Collection<E> c, Class<E> type)` | 此方法返回指定集合的动态 typesafe 视图。 |
| `checkedList(List<E> list, Class<E> type)` | 此方法返回指定列表的动态 typesafe 视图。 |
| `checkedMap(Map<K,V> m, Class<K> keyType, Class<V> valueType)` | 此方法返回指定地图的动态 typesafe 视图。 |
| `checkedNavigableMap(NavigableMap<K,V> m, Class<K> keyType, Class<V> valueType)` | 此方法返回指定可导航地图的动态 typesafe 视图。 |
| `checkedNavigableSet(NavigableSet<E> s, Class<E> type)` | 此方法返回指定导航集的动态 typesafe 视图。 |
| `checkedQueue(Queue<E> queue, Class<E> type)` | 此方法返回指定队列的动态 typesafe 视图。 |
| `checkedSet(Set<E> s, Class<E> type)` | 此方法返回指定集合的动态 typesafe 视图。 |
| `checkedSortedMap(SortedMap<K,V> m, Class<K> keyType, Class<V> valueType)` | 此方法返回指定排序地图的动态 typesafe 视图。 |
| `checkedSortedSet(SortedSet<E> s, Class<E> type)` | 此方法返回指定排序集的动态 typesafe 视图。 |
| `copy(List<? super T> dest, List<? extends T> src)` | 此方法将一个列表中的所有元素复制到另一个列表中。 |
| `disjoint(Collection<?> c1, Collection<?> c2)` | 如果两个指定的集合没有共同的元素，则此方法返回 true。 |
| `emptyEnumeration()` | 此方法返回没有元素的枚举。 |
| `emptyIterator()` | 这个方法返回一个没有元素的迭代器。 |
| `emptyList()` | 这个方法返回一个空列表(不可变的)。 |
| `emptyListIterator()` | 这个方法返回一个没有元素的列表迭代器。 |
| `emptyMap()` | 这个方法返回一个空映射(不可变的)。 |
| `emptyNavigableMap()` | 此方法返回一个空的可导航地图(不可变)。 |
| `emptyNavigableSet()` | 此方法返回一个空的可导航集(不可变)。 |
| `emptySet()` | 这个方法返回一个空集合(不可变的)。 |
| `emptySortedMap()` | 这个方法返回一个空的排序映射(不可变的)。 |
| `emptySortedSet()` | 这个方法返回一个空的排序集(不可变的)。 |
| `enumeration(Collection<T> c)` | 此方法返回指定集合的枚举。 |
| `fill(List<? super T> list, T obj)` | 此方法用指定的元素替换指定列表中的所有元素。 |
| `frequency(Collection<?> c, Object o)` | 此方法返回指定集合中等于指定对象的元素数。 |
| `indexOfSubList(List<?> source, List<?> target)` | 此方法返回指定源列表中指定目标列表的第一个匹配项的开始位置，如果没有匹配项，则返回-1。 |
| `lastIndexOfSubList(List<?> source, List<?> target)` | 此方法返回指定源列表中指定目标列表最后一次出现的起始位置，如果没有出现，则返回-1。 |
| `list(Enumeration<T> e)` | 此方法返回一个数组列表，该列表包含由指定枚举按枚举返回的顺序返回的元素。 |
| `max(Collection<? extends T> coll)` | 此方法根据给定集合元素的自然顺序返回给定集合的最大元素。 |
| `max(Collection<? extends T> coll, Comparator<? super T> comp)` | 此方法根据指定比较器引发的顺序返回给定集合的最大元素。 |
| `min(Collection<? extends T> coll)` | 这个方法根据元素的自然顺序返回给定集合的最小元素。 |
| `min(Collection<? extends T> coll, Comparator<? super T> comp)` | 此方法根据指定比较器引发的顺序返回给定集合的最小元素。 |
| `nCopies(int n, T o)` | 这个方法返回一个由指定对象的 n 个副本组成的不可变列表。 |
| `newSetFromMap(Map<E,Boolean> map)` | 此方法返回由指定映射支持的集合。 |
| `replaceAll(List<T> list, T oldVal, T newVal)` | 此方法将列表中一个指定值的所有匹配项替换为另一个。 |
| `reverse(List<?> list)` | 此方法颠倒指定列表中元素的顺序 |
| `reverseOrder()` | 此方法返回一个比较器，该比较器对实现 Comparable 接口的对象集合施加与自然排序相反的排序。 |
| `reverseOrder(Comparator<T> cmp)` | 此方法返回一个比较器，该比较器强制指定比较器的逆序。 |
| `rotate(List<?> list, int distance)` | 此方法将指定列表中的元素旋转指定的距离。 |
| `shuffle(List<?> list)` | 此方法使用默认的随机源随机置换指定的列表。 |
| `shuffle(List<?> list, Random rnd)` | 此方法使用指定的随机源随机置换指定的列表。 |
| `singletonMap(K key, V value)` | 这个方法返回一个不可变的映射，只将指定的键映射到指定的值。 |
| `singleton(T o)` | 此方法返回只包含指定对象的不可变集。 |
| `singletonList(T o)` | 这个方法返回一个只包含指定对象的不可变列表。 |
| `sort(List<T> list)` | 此方法根据元素的自然顺序，将指定列表按升序排序。 |
| `sort(List<T> list, Comparator<? super T> c)` | 此方法根据指定比较器引发的顺序对指定列表进行排序。 |
| `swap(List<?> list, int i, int j)` | 此方法交换指定列表中指定位置的元素。 |
| `synchronizedCollection(Collection<T> c)` | 此方法返回由指定集合支持的同步(线程安全)集合。 |
| `synchronizedList(List<T> list)` | 此方法返回由指定列表支持的同步(线程安全)列表。 |
| `synchronizedMap(Map<K,V> m)` | 此方法返回由指定映射支持的同步(线程安全)映射。 |
| `synchronizedNavigableMap(NavigableMap<K,V> m)` | 此方法返回由指定的可导航地图支持的同步(线程安全)可导航地图。 |
| `synchronizedNavigableSet(NavigableSet<T> s)` | 此方法返回由指定的可导航集支持的同步(线程安全)可导航集。 |
| `synchronizedSet(Set<T> s)` | 此方法返回由指定集支持的同步(线程安全)集。 |
| `synchronizedSortedMap(SortedMap<K,V> m)` | 此方法返回由指定排序映射支持的同步(线程安全)排序映射。 |
| `synchronizedSortedSet(SortedSet<T> s)` | 此方法返回由指定排序集支持的同步(线程安全)排序集。 |
| `unmodifiableCollection(Collection<? extends T> c)` | 此方法返回指定集合的不可修改视图。 |
| `unmodifiableList(List<? extends T> list)` | 此方法返回指定列表的不可修改视图。 |
| `unmodifiableNavigableMap(NavigableMap<K,V> m)` | 此方法返回指定可导航地图的不可修改视图。 |
| `unmodifiableNavigableSet(NavigableSet<T> s)` | 此方法返回指定可导航集的不可修改视图。 |
| `unmodifiableSet(Set<? extends T> s)` | 此方法返回指定集合的不可修改视图。 |
| `unmodifiableSortedMap(SortedMap<K,V> m)` | 此方法返回指定排序地图的不可修改视图。 |
| `unmodifiableSortedSet(SortedSet<T> s)` | 此方法返回指定排序集的不可修改视图。 |

现在，我们已经列出了所有的方法，所以通过 `ar`，我们有了一个模糊的提示，当考虑全局编程的观点时，我们可以感觉到这些方法有多重要。编写优化代码时重要且经常广泛使用的方法，因为在 Java 中 `Collections` 类的大量使用，您会在几乎每一个 Java 优化代码中看到这些方法。因此，在这里，更有可能的是，在任何一个类中，我们不仅要实现方法，还要讨论可以执行的操作，以便在实现方法的同时，可以有清晰的概念和强有力的命令。我们将要讨论的操作如下：

*   向集合中添加元素
*   对集合进行排序
*   在集合中搜索
*   复制元素
*   不相交集合

## 操作 1：向集合类对象添加元素

`java.util.Collections` 类的 [`addAll()`](https://www.geeksforgeeks.org/collections-addall-method-in-java-with-examples/#:~:text=The%20addAll()%20method%20of,individually%20or%20as%20an%20array.) 方法用于将所有指定的元素添加到指定的集合中。要添加的元素可以单独指定，也可以作为数组指定。

### 例

```java
// Java Program to Demonstrate Adding Elements
// Using addAll() method

// Importing required classes
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a list
        // Declaring object of string type
        List<String> items = new ArrayList<>();

        // Adding elements (items) to the list
        items.add("Shoes");
        items.add("Toys");

        // Add one or more elements
        Collections.addAll(items, "Fruits", "Bat", "Ball");

        // Printing the list contents
        for (int i = 0; i < items.size(); i++) {
            System.out.print(items.get(i) + " ");
        }
    }
}
```

**Output**

```java
Shoes Toys Fruits Bat Ball 
```

## 操作 2：整理收藏

[`Collections.sort()`](https://www.geeksforgeeks.org/collections-sort-java-examples/) 用于对集合的指定 [`List`](https://www.geeksforgeeks.org/list-interface-java-examples/) 中的元素进行升序排序。[`Collections.reverseOrder()`](https://www.geeksforgeeks.org/collections-reverseorder-java-examples/) 用于按降序排序。

### 例

```java
// Java program to demonstrate sorting
// a Collections using sort() method

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

// Main Class
// SortingCollectionExample
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a list
        // Declaring object of string type
        List<String> items = new ArrayList<>();

        // Adding elements to the list
        // using add() method
        items.add("Shoes");
        items.add("Toys");

        // Adding one or more elements using addAll()
        Collections.addAll(items, "Fruits", "Bat", "Mouse");

        // Sorting according to default ordering
        // using sort() method
        Collections.sort(items);

        // Printing the elements
        for (int i = 0; i < items.size(); i++) {
            System.out.print(items.get(i) + " ");
        }

        System.out.println();

        // Sorting according to reverse ordering
        Collections.sort(items, Collections.reverseOrder());

        // Printing the reverse order
        for (int i = 0; i < items.size(); i++) {
            System.out.print(items.get(i) + " ");
        }
    }
}
```

**Output**

```java
Bat Fruits Mouse Shoes Toys 
Toys Shoes Mouse Fruits Bat 
```

## 操作 3：在集合中搜索

[`Collections.binarySearch()`](https://www.geeksforgeeks.org/collections-binarysearch-java-examples/) 方法返回对象在排序列表中的位置。要使用此方法，列表应该按升序排序，否则，该方法返回的结果将是错误的。如果列表中存在该元素，该方法将返回该元素在排序列表中的位置，否则，该方法返回的结果将是 `-(如果存在该元素，则该元素应该存在的插入点)-1)`。

### 例

```java
// Java Program to Demonstrate Binary Search
// Using Collections.binarySearch()

// Importing required classes
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

// Main class
// BinarySearchOnACollection
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a List
        // Declaring object of string type
        List<String> items = new ArrayList<>();

        // Adding elements to object
        // using add() method
        items.add("Shoes");
        items.add("Toys");
        items.add("Horse");
        items.add("Ball");
        items.add("Grapes");

        // Sort the List
        Collections.sort(items);

        // BinarySearch on the List
        System.out.println(
            "The index of Horse is "
            + Collections.binarySearch(items, "Horse"));

        // BinarySearch on the List
        System.out.println(
            "The index of Dog is "
            + Collections.binarySearch(items, "Dog"));
    }
}
```

**Output**

```java
The index of Horse is 2
The index of Dog is -2
```

## 操作 4：复制元素

`java.util.Collections` 类的 [`copy()`](https://www.geeksforgeeks.org/collections-copy-method-in-java-with-examples/) 方法用于将一个列表中的所有元素复制到另一个列表中。操作完成后，目标列表中每个复制元素的索引将与其在源列表中的索引相同。目标列表必须至少与源列表一样长。如果较长，目标列表中的其余元素不受影响。

### 例

```java
// Java Program to Demonstrate Copying Elements
// Using copy() method

// Importing required classes
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

// Main class
// CopyOneCollectionToAnother
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Create destination list
        List<String> destination_List = new ArrayList<>();

        // Add elements
        destination_List.add("Shoes");
        destination_List.add("Toys");
        destination_List.add("Horse");
        destination_List.add("Tiger");

        // Print the elements
        System.out.println(
            "The Original Destination list is ");

        for (int i = 0; i < destination_List.size(); i++) {
            System.out.print(destination_List.get(i) + " ");
        }
        System.out.println();

        // Create source list
        List<String> source_List = new ArrayList<>();

        // Add elements
        source_List.add("Bat");
        source_List.add("Frog");
        source_List.add("Lion");

        // Copy the elements from source to destination
        Collections.copy(destination_List, source_List);

        // Printing the modified list
        System.out.println(
            "The Destination List After copying is ");

        for (int i = 0; i < destination_List.size(); i++) {
            System.out.print(destination_List.get(i) + " ");
        }
    }
}
```

**Output**

```java
The Original Destination list is 
Shoes Toys Horse Tiger 
The Destination List After copying is 
Bat Frog Lion Tiger 
```

## 操作 5：不相交集合

[`Collections.disjoint()`](https://www.geeksforgeeks.org/java-util-collections-disjoint-method-java-examples/) 用于检查两个指定的集合是否不相交。更正式地说，如果两个集合没有共同的元素，它们就是不相交的。如果两个集合没有任何共同的元素，则返回 `true`。

### 例

```java
// Java Program to Illustrate Working of Disjoint Function

// Importing required classes
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

// Main class
// DisjointCollectionsExample
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Create list1
        List<String> list1 = new ArrayList<>();

        // Add elements to list1
        list1.add("Shoes");
        list1.add("Toys");
        list1.add("Horse");
        list1.add("Tiger");

        // Create list2
        List<String> list2 = new ArrayList<>();

        // Add elements to list2
        list2.add("Bat");
        list2.add("Frog");
        list2.add("Lion");

        // Check if disjoint or not
        System.out.println(
            Collections.disjoint(list1, list2));
    }
}
```

**Output**

```java
true
```