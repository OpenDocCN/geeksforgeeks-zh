# Java 中的集合 addAll()方法，带示例

> 原文：[https://www.geeksforgeks.org/collection-addall-method-in-java-with-examples/](https://www.geeksforgeks.org/collection-addall-method-in-java-with-examples/)

`java.util.Collection` 接口的 `addAll(Collection<E> collection)` 方法用于将一个集合 `collection` 添加到该现有集合中。此方法返回一个描述操作成功与否的布尔值。如果添加了集合，则返回 `true`，否则返回 `false`。

## 语法

```java
Collection.addAll(Collection<E> collection)
```

## 参数

该方法接受一个强制参数 `collection`，该参数是一个集合，其元素将被添加到此集合中。

## 返回值

这个方法返回一个布尔值，描述操作的成功。如果添加了集合，则返回 `true`，否则返回 `false`。

## 异常

如果此集合不支持添加操作，可能抛出以下异常：

*   `ClassCastException`：如果指定元素的类阻止其被添加到此集合中。
*   `NullPointerException`：如果指定元素为空且此集合不允许空元素。
*   `IllegalArgumentException`：如果元素的某个属性阻止其被添加到此集合。
*   `IllegalStateException`：如果由于插入限制，此时无法添加元素。

以下示例说明了 `Collection.addAll()` 方法：

### 示例 1：使用 LinkedList 类

```java
// Java code to illustrate boolean addAll()

import java.util.*;

public class LinkedListDemo {
    public static void main(String args[])
    {
        // Creating an empty LinkedList
        Collection<String> list = new LinkedList<String>();

        // A collection is created
        Collection<String> collect = new LinkedList<String>();
        collect.add("A");
        collect.add("Computer");
        collect.add("Portal");
        collect.add("for");
        collect.add("Geeks");

        // Displaying the list
        System.out.println("The LinkedList is: " + list);

        // Appending the collection to the list
        list.addAll(collect);

        // displaying the modified LinkedList
        System.out.println("The new linked list is: " + list);
    }
}
```

输出：

```
The LinkedList is: []
The new linked list is: [A, Computer, Portal, for, Geeks]
```

### 示例 2：使用 ArrayDeque 类

```java
// Java code to illustrate addAll() method

import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Collection<String> de_que = new ArrayDeque<String>();

        // Creating a new ArrayDeque
        Collection<String> deque = new ArrayDeque<String>();
        deque.add("Welcome");
        deque.add("To");
        deque.add("Geeks");
        deque.add("4");
        deque.add("Geeks");

        // Displaying the list
        System.out.println("The ArrayDeque is: " + de_que);

        // Appending the collection to the list
        de_que.addAll(deque);

        // displaying the modified ArrayDeque
        System.out.println("The new ArrayDeque is: " + de_que);
    }
}
```

输出：

```
The ArrayDeque is: []
The new ArrayDeque is: [Welcome, To, Geeks, 4, Geeks]
```

### 示例 3：使用 ArrayList 类

```java
// Java code to illustrate boolean addAll()

import java.util.*;

public class ArrayListDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayList
        Collection<String> list = new ArrayList<String>();

        // A collection is created
        Collection<String> collect = new ArrayList<String>();
        collect.add("A");
        collect.add("Computer");
        collect.add("Portal");
        collect.add("for");
        collect.add("Geeks");

        // Displaying the list
        System.out.println("The ArrayList is: " + list);

        // Appending the collection to the list
        list.addAll(collect);

        // displaying the modified ArrayList
        System.out.println("The new ArrayList is: " + list);
    }
}
```

输出：

```
The ArrayList is: []
The new ArrayList is: [A, Computer, Portal, for, Geeks]
```

### 示例 4：演示 NullPointerException

```java
// Java code to illustrate boolean addAll()

import java.util.*;

public class NullPointerExceptionDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayList
        Collection<String> list = new ArrayList<String>();

        // A collection is created
        Collection<String> collect = null;

        // Displaying the list
        System.out.println("The ArrayList is: " + list);

        try {
            // Appending the collection to the list
            list.addAll(collect);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

输出：

```
The ArrayList is: []
Exception: java.lang.NullPointerException
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/util/Collection.html#addAll-java.util.Collection-](https://docs.oracle.com/javase/9/docs/api/java/util/Collection.html#addAll-java.util.Collection-)