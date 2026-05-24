# Java 中 TreeMap 和 TreeSet 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-treemap-and-treeset-in-java/](https://www.geeksforgeeks.org/difference-between-treemap-and-treeset-in-java/)

[`TreeSet`](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 主要是 Java 中 `SortedSet` 的一个实现，不允许重复，对象以排序和升序的方式存储。

`TreeSet` 的一些重要特征是:
*   在 `TreeSet` 中不允许重复值，因为它实现了 [`SortedSet`](https://www.geeksforgeeks.org/sortedset-java-examples/) 接口。
*   `TreeSet` 中的对象以升序存储。
*   在 `TreeSet` 中，元素的插入顺序不保持不变。

[`TreeMap`](https://www.geeksforgeeks.org/treemap-in-java/) 是 `Map` 接口的一个实现。`TreeMap` 也是 `NavigableMap` 和 `AbstractMap` 类的实现。

`TreeMap` 的一些重要特征是:
*   在 `TreeMap` 中，空键（如 `Map`）是不允许的，因此抛出 [`NullPointerException`](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)（多个空值可能与不同的键相关联）。
*   `TreeMap` 不支持 [`Entry.setValue`](https://www.geeksforgeeks.org/map-entry-interface-java-example/) 方法。

下面是 Java 中的 `TreeSet` 和 `TreeMap` 的图示:

### 示例 1

```java
// Illustration of TreeMap and TreeSet in Java
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        TreeSet<Integer> set = new TreeSet<>();
        set.add(3);
        set.add(4);
        set.add(3);
        set.add(5);

        TreeMap<Integer, Integer> tm = new TreeMap<>();
        tm.put(2, 4);
        tm.put(3, 5);
        tm.put(4, 5);
        tm.put(2, 3);
        System.out.println(set);
        System.out.println(tm);
    }
}
```

**Output**

```java
[3, 4, 5]
{2=3, 3=5, 4=5}
```

### 示例 2

```java
// Illustration of TreeMap and TreeSet in Java
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        TreeSet<String> l = new TreeSet<>();
        l.add("geeks");
        l.add("FOR");
        l.add("geeks");
        l.add("tutorial");

        TreeMap<Integer, String> l1 = new TreeMap<>();

        l1.put(1, "geeks");
        l1.put(2, "FOR");
        l1.put(3, "geeks");
        l1.put(4, "tutorial");
        System.out.println(l);
        System.out.println(l1);
    }
}
```

**Output**

```java
[FOR, geeks, tutorial]
{1=geeks, 2=FOR, 3=geeks, 4=tutorial}
```

| 序号 | `TreeSet` | `TreeMap` |
| :--- | :--- | :--- |
| 1. | `TreeSet` 在 Java 中实现了 `SortedSet`。 | `TreeMap` 在 Java 中实现 `Map` 接口。 |
| 2. | `TreeSet` 在 Java 中存储一个对象。 | `TreeMap` 存储两个对象：一个键和一个值。 |
| 3. | `TreeSet` 不允许在 Java 中复制对象。 | Java 中的 `TreeMap` 允许重复值。 |
| 4. | `TreeSet` 在 Java 中实现了 `NavigableSet`。 | `TreeMap` 在 Java 中实现了 `NavigableMap`。 |
| 5. | `TreeSet` 基于对象进行排序。 | `TreeMap` 是根据关键字排序的。 |