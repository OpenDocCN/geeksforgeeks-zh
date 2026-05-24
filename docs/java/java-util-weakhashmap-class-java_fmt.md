# Java 中的 WeakHashMap 类

> 原文：[https://www.geeksforgeeks.org/java-util-weakhashmap-class-java/](https://www.geeksforgeeks.org/java-util-weakhashmap-class-java/)

`WeakHashMap` 是 `Map` 接口的基于哈希表的实现，带有弱键。当一个条目的密钥不再被正常使用时，它将被自动删除。更准确地说，给定键的映射的存在不会阻止该键被垃圾收集器丢弃，也就是说，使其成为可终结的、最终确定的，然后被回收。当一个键被丢弃时，它的条目实际上从映射中被移除，因此这个类的行为与其他映射实现有些不同。

### WeakHashMap 的几个重要特征

*   `WeakHashMap` 支持空值和空键。
*   它没有同步。
*   此类主要用于其 `equals` 方法使用 `==` 运算符测试对象标识的键对象。

### WeakHashMap 中的构造函数

**1. `WeakHashMap()`:** 此构造函数用于创建一个空的 `WeakHashMap`，默认初始容量为 `16`，负载系数为 `0.75`。

**2. `WeakHashMap(int initialCapacity)`:** 此构造函数用于创建一个给定初始容量和默认负载系数 `0.75` 的空 `WeakHashMap`。

**3. `WeakHashMap(int initialCapacity, float loadFactor)`:** 此构造函数用于创建具有给定初始容量和给定负载系数的空 `WeakHashMap`。

**4. `WeakHashMap(Map m)`:** 此构造函数用于创建一个新的 `WeakHashMap`，其映射与指定的映射相同。

### WeakHashMap 中的方法

| 方法 | 已执行的操作 |
| --- | --- |
| `clear()` | 从此映射中移除所有映射。该调用返回后，地图将为空。 |
| `containsValue(Object value)` | 如果此映射将一个或多个键映射到指定值，则返回 `true`。 |
| `containsKey(Object key)` | 如果此映射包含指定键的映射，则返回 `true`。 |
| `entrySet()` | 返回此映射中包含的映射的集合视图。集合由地图支持，因此对地图的更改会反映在集合中，反之亦然。如果在对集合进行迭代的过程中修改了映射（除了通过迭代器自己的移除操作，或者通过迭代器返回的映射条目上的 `setValue` 操作），迭代的结果是未定义的。集合支持元素移除，通过迭代器移除、集合移除、全部移除、保留和清除操作从映射中移除相应的映射。它不支持 `add` 或 `addAll` 操作。 |
| `get(Object key)` | 返回指定键映射到的值，如果此映射不包含键映射，则返回 `null`。 |
| `isEmpty()` | 如果此映射不包含键值映射，则返回 `true`。这是一个快照，可能不会反映未处理的条目，这些条目将在下一次尝试访问之前被删除，因为它们不再被引用。 |
| `keySet()` | 返回此地图中包含的键的集合视图。集合由地图支持，因此对地图的更改会反映在集合中，反之亦然。如果在对集合进行迭代时修改了映射（通过迭代器自己的移除操作除外），迭代的结果是未定义的。集合支持元素移除，通过迭代器移除、集合移除、全部移除、保留和清除操作从映射中移除相应的映射。它不支持 `add` 或 `addAll` 操作。 |
| `put(K key, V value)` | 将指定值与此映射中的指定键相关联。如果映射先前包含此键的映射，旧值将被替换。 |
| `putAll(Map m)` | 将指定映射中的所有映射复制到此映射。这些映射将替换此映射对当前指定映射中的任何键的任何映射。 |
| `remove(Object key)` | 从该弱哈希映射中删除某个键的映射（如果存在）。更正式地说，如果这个映射包含从键 `k` 到值 `v` 的映射，那么 `(key==null ? k==null : key.equals(k))`，则删除该映射。 |
| `size()` | 返回此映射中键值映射的数量。这是一个快照，可能不会反映未处理的条目，这些条目将在下一次尝试访问之前被删除，因为它们不再被引用。 |
| `values()` | 返回此地图中包含的值的集合视图。集合由地图支持，因此对地图的更改会反映在集合中，反之亦然。如果在集合的迭代过程中修改了映射（通过迭代器自己的移除操作除外），迭代的结果是未定义的。集合支持元素移除，通过迭代器移除、集合移除、移除所有、保留和清除操作从映射中移除相应的映射。它不支持 `add` 或 `addAll` 操作。 |

### 示例 1

```java
// Java Program to Illustrate WeakHashMap class
// Via close(), containsValue(), containsKey()
// and isEmpty() method

// Importing required classes
import java.util.Map;
import java.util.WeakHashMap;

// Main class
// WeakHashMapdemo
class GFG {

    // Main driver method
    public static void main(String[] arg)
    {

        // Creating an empty WeakHashMap
        // of Number and string type
        Map<Number, String> weak
            = new WeakHashMap<Number, String>();

        // Inserting custom elements
        // using put() method
        weak.put(1, "geeks");
        weak.put(2, "for");
        weak.put(3, "geeks");

        // Printing and alongside checking weak map
        System.out.println("our weak map: " + weak);

        // Checking if "for" exist
        if (weak.containsValue("for"))
            System.out.println("for exist");

        // Checking if 1 exist as a key in Map
        if (weak.containsKey(1))
            System.out.println("1 exist");

        // Removing all data
        // using clear() method
        weak.clear();

        // Checking whether the Map is empty or not
        // using isEmpty() method
        if (weak.isEmpty())

            // Display message for better readability
            System.out.println("empty map: " + weak);
    }
}
```

**输出**

```java
our weak map: {3=geeks, 2=for, 1=geeks}
for exist
1 exist
empty map: {}
```

### 示例 2

```java
// Java Program to Illustrate WeakHashMap class
// Via entrySet(), keySet() and Values() Method

// Importing required classes
import java.util.Collection;
import java.util.Map;
import java.util.Set;
import java.util.WeakHashMap;

// Main class
// WeakHashMapdemo
class GFG {

    // Main driver method
    public static void main(String[] arg)
    {

        // Creating an empty WeakHashMap
        // of number and string type
        Map<Number, String> weak
            = new WeakHashMap<Number, String>();

        // Inserting elements
        // using put() method
        weak.put(1, "geeks");
        weak.put(2, "for");
        weak.put(3, "geeks");

        // Creating object of Set interface
        Set set1 = weak.entrySet();

        // Checking above Set
        System.out.println(set1);

        // Creating set for key
        Set keySet = weak.keySet();

        // Checking keySet
        System.out.println("key set: " + keySet);

        Collection value = weak.values();

        // Checking values of map and printing them
        System.out.println("values: " + value);
    }
}
```

**输出**

```java
[3=geeks, 2=for, 1=geeks]
key set: [3, 2, 1]
values: [geeks, for, geeks]
```

### 示例 3

```java
// Java code remove(), putAll()
// get() and size() method

import java.util.Collection;
import java.util.Map;
import java.util.Set;
import java.util.WeakHashMap;

class WeakHashMapdemo {
    public static void main(String[] arg)
    {
        Map<Number, String> weak
            = new WeakHashMap<Number, String>();
        weak.put(1, "geeks");
        weak.put(2, "for");
        weak.put(3, "geeks");

        Map<Number, String> weak1
            = new WeakHashMap<Number, String>();
        weak1.putAll(weak);

        // Getting value of key 2
        System.out.println(weak1.get(2));

        // Printing the size of map
        // using size() method
        System.out.println("Size of map is: "
                           + weak1.size());

        // Removing second element
        // using standard remove() method
        weak1.remove(2);

        // Printing the size after removing key and value
        // pair
        System.out.println("Size after removing: "
                           + weak1.size());
    }
}
```

**输出**

```java
for
Size of map is: 3
Size after removing: 2
```

本文由 **阿比舍克·维尔马** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](http://www.write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `review-team@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。