# Java 中的 LinkedList addAll()方法

> 原文: [https://www.geeksforgeeks.org/java-util-linkedlist-addall-method-in-java/](https://www.geeksforgeeks.org/java-util-linkedlist-addall-method-in-java/)

## 1. `java.util.LinkedList.addAll(Collection C)`
此方法用于将作为参数传递给此函数的集合中的所有元素附加到列表的末尾，同时保持集合迭代器返回的顺序。

**语法:**
```java
boolean addAll(Collection C)
```

**参数:** 参数`C`是数组列表的集合。它是需要在列表末尾追加元素的集合。

**返回值:** 如果至少执行了一个追加动作，则该方法返回真。

下面的程序说明了`Java.util.LinkedList.addAll()`方法:
```java
// Java code to illustrate boolean addAll()
import java.util.*;
import java.util.LinkedList;
import java.util.ArrayList;

public class LinkedListDemo {
    public static void main(String args[]) {
        // Creating an empty LinkedList
        LinkedList<String> list = new LinkedList<String>();

        // Use add() method to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        // A collection is created
        Collection<String> collect = new ArrayList<String>();
        collect.add("A");
        collect.add("Computer");
        collect.add("Portal");
        collect.add("for");
        collect.add("Geeks");

        // Displaying the list
        System.out.println("The LinkedList is: " + list);

        // Appending the collection to the list
        list.addAll(collect);

        // Clearing the list using clear() and displaying
        System.out.println("The new linked list is: " + list);
    }
}
```

**Output:**
```java
The LinkedList is: [Geeks, for, Geeks, 10, 20]
The new linked list is: [Geeks, for, Geeks, 10, 20, A, Computer, Portal, for, Geeks]
```

## 2. `java.util.LinkedList.addAll(int index, Collection C)`
此方法用于将作为参数传递给此函数的集合中的所有元素附加到列表的特定索引或位置。

**语法:**
```java
boolean addAll(int index, Collection C)
```

**参数:** 该函数接受两个参数，如上语法所示，描述如下。
*   `index`: 该参数为整数数据类型，指定列表中从容器元素插入位置开始的位置。
*   `C`: 是数组列表的集合。它是需要追加元素的集合。

**返回值:** 如果至少执行了一个追加操作，则该方法返回真。

下面的程序说明了`Java.util.LinkedList.addAll()`方法:
```java
// Java code to illustrate boolean addAll()
import java.util.*;
import java.util.LinkedList;
import java.util.ArrayList;

public class LinkedListDemo {
    public static void main(String args[]) {
        // Creating an empty LinkedList
        LinkedList<String> list = new LinkedList<String>();

        // Use add() method to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        // Creating a Collection
        Collection<String> collect = new ArrayList<String>();
        collect.add("A");
        collect.add("Computer");
        collect.add("Portal");
        collect.add("for");
        collect.add("Geeks");

        // Displaying the list
        System.out.println("The LinkedList is: " + list);

        // Appending the collection to the list
        list.addAll(1, collect);

        // Clearing the list using clear() and displaying
        System.out.println("The new linked list is: " + list);
    }
}
```

**Output:**
```java
The LinkedList is: [Geeks, for, Geeks, 10, 20]
The new linked list is: [Geeks, A, Computer, Portal, for, Geeks, for, Geeks, 10, 20]
```