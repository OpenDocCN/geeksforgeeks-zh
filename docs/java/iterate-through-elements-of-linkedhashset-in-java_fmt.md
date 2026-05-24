# 遍历 Java 中 LinkedHashSet 的元素

> 原文: [https://www.geeksforgeeks.org/iterate-through-elements-of-linkedhashset-in-java/](https://www.geeksforgeeks.org/iterate-through-elements-of-linkedhashset-in-java/)

[`LinkedHashSet`](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 是 [`HashSet`](https://www.geeksforgeeks.org/hashset-in-java/) 的有序版本，它维护所有元素的双向链表。当需要维护迭代顺序时，使用这个类。

**例:**

```java
Input: 
["Geeks", "for", "Geeks"]

Output:
Geeks
for
Geeks

Input: 
[9, 4, 6, 2, 8]

Output:

```

**迭代 LinkedHashSet 元素的不同方式:**

1.  使用 for-each 循环
2.  使用迭代器
3.  使用 JDK 1.8 Stream

## 方法 1: 使用 for-each 循环

```java
// Java Program to Iterate through linkedHashset
// Using the for-each loop

import java.io.*;
import java.util.LinkedHashSet;

class GFG {
    public static void main(String[] args)
    {

        LinkedHashSet<String> gfg
            = new LinkedHashSet<String>();

        // Adding element to LinkedHashSet
        gfg.add("Geeks");
        gfg.add("for");
        gfg.add("geeks");

        // iterating LinkedHashSet using enhanced for loop
        for (String itr : gfg) {
            System.out.println(itr);
        }
    }
}
```

**输出**

```java
Geeks
for
geeks
```

## 方法 2: 使用迭代器

使用 [`Iterator`](https://www.geeksforgeeks.org/iterators-in-java/) 方法遍历 `LinkedHashSet` 的元素。我们将使用 `hasNext()` 方法和 `next()` 方法以及 `while` 循环来迭代 `LinkedHashSet` 元素。

**类型参数:**

*   **E** – 此集合维护的元素类型。

**语法:**

```java
public Iterator<E> iterator()
```

**返回:** 这个方法按照与输入相同的顺序返回 `LinkedHashSet` 的元素。

```java
// Java code to demonstrate 
// the iterating over LinkedHashSet 
// Using iterators

import java.io.*; 
import java.util.*;

class IteratingLinkedHashSet {

    public static void main(String[] args) 
    { 
        // Instantiate an object of Set 
        // Since LinkedHashSet implements Set 
        // Set points to LinkedHashSet 
        Set<String> gfg = new LinkedHashSet<String>();

        // Elements are added using add() method 
        gfg.add("Geek"); 
        gfg.add("For"); 
        gfg.add("Geeks"); 
        gfg.add("Courses"); 
        gfg.add("Interview Prep"); 
        gfg.add("Doubt Classes");

        // Iterating through the LinkedHashSet 
        Iterator itr = gfg.iterator();

        while (itr.hasNext()){
            System.out.println( itr.next() );
        }
    }
}
```

**输出**

```java
Geek
For
Geeks
Courses
Interview Prep
Doubt Classes
```

## 方法 3: 使用 JDK 1.8 Stream

使用 `forEach` 方法迭代 `LinkedHashSet` 的元素。我们将使用 Stream 遍历整个内容。Stream 表示来自源的对象序列，支持聚合操作。

**语法:**

```java
set.stream().forEach()
```

**返回:** 返回以集合为源的顺序流。

```java
// Java code to demonstrate
// the iterating over LinkedHashSet
// Using JDK 1.8 streams

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        LinkedHashSet<Integer> gfg = new LinkedHashSet<Integer>();

        // Elements are added using add() method
        gfg.add(9);
        gfg.add(7);
        gfg.add(11);
        gfg.add(43);
        gfg.add(2);

        // Using forEach Method using Stream.
        gfg.stream().forEach(System.out::println);
    }
}
```

**输出**

```java

```

**时间复杂度:** O(N)，其中 N 是 `LinkedHashSet` 的元素个数。