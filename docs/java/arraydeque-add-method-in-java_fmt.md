# Java 中 ArrayDeque add()方法

> 原文：[`https://www.geeksforgeeks.org/arraydeque-add-method-in-java/`](https://www.geeksforgeeks.org/arraydeque-add-method-in-java/)

Java 中的 [`ArrayDeque.add(Object element)`](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayDeque.html#add-E-) 方法是用来在 [`Deque`](https://docs.oracle.com/javase/8/docs/api/java/util/Deque.html) 的末尾添加一个特定的元素。该函数类似于 Java 中 [`ArrayDeque`](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayDeque.html) 的 [`addLast()`](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayDeque.html#addLast-E-) 方法。

## 语法

```java
ArrayDeque.add(Object element)
```

## 参数

参数 `element` 的类型为 [`ArrayDeque`](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayDeque.html)，指的是要添加到 [`Deque`](https://docs.oracle.com/javase/8/docs/api/java/util/Deque.html) 的元素。

## 返回值

如果元素被成功添加到 [`deque`](https://docs.oracle.com/javase/8/docs/api/java/util/Deque.html) 中，函数返回 `true`，否则返回 `false`。

## 异常

如果传递的参数为 `null`，该方法将抛出 [`NullPointerException`](https://docs.oracle.com/javase/8/docs/api/java/lang/NullPointerException.html)。

下面的程序说明了 [`java.util.ArrayDeque.add()`](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayDeque.html#add-E-) 方法：

### 程序 1：将字符串元素添加到 Deque 中

```java
// Java code to illustrate add()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<String> de_que = new ArrayDeque<String>();

        // Use add() method to add elements into the Deque
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("4");
        de_que.add("Geeks");

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);
    }
}
```

**Output:**

```java
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
```

### 程序 2：将整数元素加入到 Deque 中

```java
// Java code to illustrate add()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Use add() method to add elements into the Deque
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);
    }
}
```

**Output:**

```java
ArrayDeque: [10, 15, 30, 20, 5]
```