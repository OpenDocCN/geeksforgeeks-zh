# Java 中的 ConcurrentSkipListSet subSet()方法

> 原文: [https://www.geeksforgeeks.org/concurrentskiplistset-subset-method-in-java/](https://www.geeksforgeeks.org/concurrentskiplistset-subset-method-in-java/)

## subSet(E fromElement, E toElement)

`java.util.concurrent.ConcurrentSkipListSet` 的 `subSet()` 方法是 Java 中的一个内置函数，它返回该集合中元素范围为从 `fromElement` (包含) 到 `toElement` (不包含) 的部分的视图。(如果 `fromElement` 和 `toElement` 相等，则返回的集合为空。)返回的集合由该集合支持，因此返回集合中的变化反映在该集合中，反之亦然。返回的集合支持该集合支持的所有可选集合操作。

**语法:**

```java
public NavigableSet subSet(E fromElement,
                     E toElement) 
```

**参数:** 函数接受以下参数:

*   `fromElement` – 返回集合的低端点(含)。
*   `toElement` – 返回集合的高端点(不含)。

**返回值:** 该函数返回一个 `NavigableSet`，它是该集合的一部分的视图，该集合的元素范围从 `fromElement` (包含)到 `toElement` (不包含)。

**异常:** 函数抛出以下异常:

*   `ClassCastException` – 如果 `fromElement` 和 `toElement` 无法使用该集合的比较器进行相互比较(或者，如果该集合没有比较器，则使用自然排序)。如果 `fromElement` 或 `toElement` 无法与集合中当前的元素进行比较，则实现可能会引发此异常，但这不是必需的。
*   `NullPointerException` – 如果 `fromElement` 或 `toElement` 为空。
*   `IllegalArgumentException` – 如果 `fromElement` 大于 `toElement`；或者如果此集合本身具有受限范围，并且 `fromElement` 或 `toElement` 位于范围界限之外。

下面的程序说明了 `ConcurrentSkipListSet.subSet()` 方法:

**程序 1:**

```java
// Java program to demonstrate subSet()
// method of ConcurrentSkipListSet
import java.util.NavigableSet;
import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetSubSetExample1 {
    public static void main(String[] args)
    {
        // Initializing the set
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        for (int i = 0; i <= 10; i++)
            set.add(i);

        // Printing the elements of the set
        System.out.println("Contents of the set: " + set);

        // Creating a subset object
        NavigableSet<Integer> sub_set = set.subSet(2, 8);

        // Printing the elements of the subset
        System.out.println("Contents of the subset: " + sub_set);
    }
}
```

**Output:**

```java
Contents of the set: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
Contents of the subset: [2, 3, 4, 5, 6, 7]
```

**程序 2:**

```java
// Java program to demonstrate subSet()
// method of ConcurrentSkipListSet
import java.util.NavigableSet;
import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetSubSetExample2 {
    public static void main(String[] args)
    {
        // Initializing the set
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        for (int i = 0; i <= 10; i++)
            set.add(i);

        // Printing the elements of the set
        System.out.println("Contents of the set: " + set);

        try {
            // Creating a subset object
            NavigableSet<Integer> sub_set = set.subSet(2, null);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Contents of the set: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
Exception: java.lang.NullPointerException
```

## subSet(E fromElement, boolean fromInclusive, E toElement, boolean toInclusive)

`java.util.concurrent.ConcurrentSkipListSet` 的 `subSet()` 方法是 Java 中的一个内置函数，它返回该集合中元素范围为从一个元素到另一个元素的部分的视图。如果 `fromElement` 和 `toElement` 相等，则返回的集合为空，除非 `fromInclusive` 和 `toInclusive` 都为真。返回的集合由该集合支持，因此返回集合中的更改反映在该集合中，反之亦然。返回的集合支持该集合支持的所有可选集合操作。返回的集合将在试图插入超出其范围的元素时抛出一个 `IllegalArgumentException`。

**语法:**

```java
public NavigableSet subSet(E fromElement,
                         boolean fromInclusive,
                         E toElement,
                         boolean toInclusive) 
```

**参数:** 函数接受以下参数:

*   `fromElement` – 返回集合的低端点。
*   `fromInclusive` – 如果低端点将包含在返回的视图中，则为真。
*   `toElement` – 返回集合的高端点。
*   `toInclusive` – 如果高端点将包含在返回的视图中，则为真。

**返回值:** 该函数返回该集合部分的视图，该集合的元素范围为从 `fromElement` 到 `toElement`。

**异常:** 函数抛出以下异常:

*   `ClassCastException` – 如果 `fromElement` 和 `toElement` 无法使用该集合的比较器进行相互比较(或者，如果该集合没有比较器，则使用自然排序)。如果 `fromElement` 或 `toElement` 无法与集合中当前的元素进行比较，则实现可能会引发此异常，但这不是必需的。
*   `NullPointerException` – 如果 `fromElement` 或 `toElement` 为空。
*   `IllegalArgumentException` – 如果 `fromElement` 大于 `toElement`；或者如果此集合本身具有受限范围，并且 `fromElement` 或 `toElement` 位于范围界限之外。

下面的程序说明了 `ConcurrentSkipListSet.subSet()` 方法:

**程序 3:**

```java
// Java Program Demonstrate subSet()
// method of ConcurrentSkipListSet
import java.util.NavigableSet;
import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetSubSetExample3 {
    public static void main(String[] args)
    {
        // Initializing the set
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        for (int i = 0; i <= 10; i++)
            set.add(i);

        // Printing the elements of the set
        System.out.println("Contents of the set: " + set);

        // Creating a subset object
        NavigableSet<Integer> sub_set = set.subSet(2, true, 8, true);

        // Printing the elements of the subset
        System.out.println("Contents of the subset: " + sub_set);
    }
}
```

**Output:**

```java
Contents of the set: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
Contents of the subset: [2, 3, 4, 5, 6, 7, 8]
```

**参考:**
[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#subSet-E-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#subSet-E-E-)

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#subSet-E-boolean-E-boolean-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#subSet-E-boolean-E-boolean-)