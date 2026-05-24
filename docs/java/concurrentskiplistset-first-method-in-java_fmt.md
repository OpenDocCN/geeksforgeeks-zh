# Java 中的 ConcurrentSkipListSet first()方法

> 原文: [https://www.geeksforgeeks.org/concurrentskiplistset-first-method-in-java/](https://www.geeksforgeeks.org/concurrentskiplistset-first-method-in-java/)

`java.util.concurrent.ConcurrentSkipListSet` 的 `first()` 方法是 Java 中的一个内置函数，它返回当前在这个集合中的第一个(最低的)元素。

**语法:**

```java
ConcurrentSkipListSet.first()
```

**返回值:** 函数返回当前在这个集合中的第一个(最低的)元素。

**异常:** 如果该集合为空，函数抛出 `NoSuchElementException`。

下面的程序说明了 `ConcurrentSkipListSet.first()` 方法:

**程序 1:**

```java
// Java Program Demonstrate first()
// method of ConcurrentSkipListSet

import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetFirstExample1 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to first set
        set.add(10);
        set.add(35);
        set.add(20);
        set.add(25);

        System.out.println("The lowest element in the set: "
                           + set.first());
    }
}
```

**Output:**

```java
The lowest element in the set: 10
```

**程序 2:** 程序先显示 `NoSuchElementException()`。

```java
// Java Program Demonstrate first()
// method of ConcurrentSkipListSet

import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetFirstExample2 {
    public static void main(String[] args) throws InterruptedException
    {

        // Initializing the set
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();
        try {
            System.out.println("The lowest element in the set: " +
                               set.first());
        }
        catch (Exception e) {
            System.out.println("Exception :" + e);
        }
    }
}
```

**Output:**

```java
Exception :java.util.NoSuchElementException
```

**参考:** [https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#first--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#first--)