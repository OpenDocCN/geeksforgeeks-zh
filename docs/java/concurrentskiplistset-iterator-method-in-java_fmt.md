# Java 中的 ConcurrentSkipListSet iterator() 方法

> 原文: [https://www.geeksforgeeks.org/concurrentskiplistset-iterator-method-in-java/](https://www.geeksforgeeks.org/concurrentskiplistset-iterator-method-in-java/)

`java.util.concurrent.ConcurrentSkipListSet` 的 `iterator()` 方法是 Java 中的内置函数，用于以升序返回该集合中元素的迭代器。

## 语法

```java
ConcurrentSkipListSet.iterator()
```

## 返回值

函数以升序返回该集合中元素的迭代器。

下面的程序说明了 `java.util.concurrent.ConcurrentSkipListSet.iterator()`:

## 程序 1

```java
// Java Program Demonstrate iterator()
// method of ConcurrentSkipListSet

import java.util.Iterator;
import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetIteratorExample1 {
    public static void main(String[] args)
    {

// Initializing the set
        ConcurrentSkipListSet<String>
            set = new ConcurrentSkipListSet<String>();

// Adding elements to this set
        set.add("Gfg");
        set.add("is");
        set.add("fun!!");

// Returns an iterator over the elements
        Iterator<String> iterator = set.iterator();

// Printing the elements of the set
        while (iterator.hasNext())
            System.out.print(iterator.next() + " ");
    }
}
```

## Output

```java
Gfg fun!! is
```