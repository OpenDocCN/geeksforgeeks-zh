# Java 中的 NavigableSet subSet()方法

> 原文: [https://www.geeksforgeeks.org/navigableset-subset-method-in-java/](https://www.geeksforgeeks.org/navigableset-subset-method-in-java/)

Java 中 `NavigableSet` 接口的 `subSet()` 方法用于返回该集合中元素范围从 `fromElement` 到 `toElement` 的部分的视图。

*   如果 `fromElement` 和 `toElement` 相等，返回的集合为空，除非 `fromInclusive` 和 `toInclusive` 均为 `true`。
*   返回的集合由此集合支持，因此对返回集合的更改会反映在此集合中，反之亦然。
*   返回的集合支持此集合支持的所有可选集合操作。

**注意**: 返回的集合将在试图插入其范围之外的元素时抛出一个 `IllegalArgumentException`。

## 语法

```java
NavigableSet<E> subSet(E fromElement,
                       boolean fromInclusive,
                       E toElement,
                       boolean toInclusive);
```

其中，`E` 是此 `Set` 容器维护的元素类型。

## 参数

该函数接受 4 个参数，解释如下:

*   **`fromElement`**: 这是一个必选参数，指定返回集合的低端点。
*   **`fromInclusive`**: 这是一个可选的布尔类型参数。如果设置为 `true`，低端点将包含在返回的视图中，否则不包含。
*   **`toElement`**: 这是一个必选参数，指定返回集合的高端点。
*   **`toInclusive`**: 这是一个可选的布尔类型参数。如果设置为 `true`，高端点将包含在返回的视图中，否则不包含。

## 返回值

返回该集合中元素范围为从 `fromElement` 到 `toElement` 的部分的视图。

## 程序示例

下面的程序说明了 Java 中的 `subSet()` 方法:

### 程序 1: 带整数元素的 NavigableSet

```java
// A Java program to demonstrate
// subSet() method of NavigableSet

import java.util.NavigableSet;
import java.util.TreeSet;

public class GFG {
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

        System.out.println("Map with key-value between the given argument : "
                           + ns.subSet(1, 6));

        System.out.println("Map with key-value between the given argument : "
                           + ns.subSet(2, 6));
    }
}
```

**输出:**

```java
Map with key-value between the given argument : [1, 2, 3, 4, 5]
Map with key-value between the given argument : [2, 3, 4, 5]
```

### 程序 2: 带字符串元素的 NavigableSet

```java
// A Java program to demonstrate
// subSet() method of NavigableSet

import java.util.NavigableSet;
import java.util.TreeSet;

public class GFG {
    public static void main(String[] args)
    {
        NavigableSet<String> ns = new TreeSet<>();
        ns.add("A");
        ns.add("B");
        ns.add("C");
        ns.add("D");
        ns.add("E");
        ns.add("F");
        ns.add("G");

        System.out.println("Map with key-value between the given range : "
                           + ns.subSet("B", "G"));
    }
}
```

**输出:**

```java
Map with key-value between the given range : [B, C, D, E, F]
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#subSet(E, E)](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#subSet(E, E))