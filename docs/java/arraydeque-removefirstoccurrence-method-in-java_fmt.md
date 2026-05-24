# Java 中的 ArrayDeque removeFirstOccurrence() 方法

> 原文：[https://www.geeksforgeeks.org/arraydeque-removefirstoccurrence-method-in-java/](https://www.geeksforgeeks.org/arraydeque-removefirstoccurrence-method-in-java/)

`java.util.ArrayDeque.removeFirstOccurrence(Object)` 方法用于从该双端队列中移除特定元素的第一次出现。如果该元素存在并被移除，则返回 `true`；如果未找到该元素，则返回 `false`。

## 语法

```java
ArrayDeque.removeFirstOccurrence(Object o)
```

## 参数

该方法接受一个 `Object` 类型的参数 `o`，表示要从双端队列中移除第一次出现的元素。

## 返回值

如果元素存在于双端队列中，该方法返回 `true`，否则返回 `false`。

下面的程序说明了 `java.util.ArrayDeque.removeFirstOccurrence()` 方法：

## 程序 1

```java
// Java code to illustrate removeFirstOccurrence()
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
        de_que.add("For");
        de_que.add("Geeks");

        // Displaying the ArrayDeque
        System.out.println("Initial ArrayDeque: " + de_que);

        // Removing elements using removeFirstOccurrence() method
        de_que.removeFirstOccurrence("Geeks");
        de_que.removeFirstOccurrence("For");

        // Displaying the ArrayDeque after removal
        System.out.println("ArrayDeque after removing "
                           + "elements: " + de_que);
    }
}
```

**输出：**

```java
Initial ArrayDeque: [Welcome, To, Geeks, For, Geeks]
ArrayDeque after removing elements: [Welcome, To, Geeks]
```

## 程序 2

```java
// Java code to illustrate removeFirstOccurrence()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Use add() method to add elements into the Deque
        de_que.add(10);
        de_que.add(10);
        de_que.add(30);
        de_que.add(10);
        de_que.add(30);

        // Displaying the ArrayDeque
        System.out.println("Initial ArrayDeque: " + de_que);

        // Removing elements using removeFirstOccurrence() method
        de_que.removeFirstOccurrence(30);
        de_que.removeFirstOccurrence(5);

        // Displaying the ArrayDeque after removal
        System.out.println("ArrayDeque after removing "
                           + "elements: " + de_que);
    }
}
```

**输出：**

```java
Initial ArrayDeque: [10, 10, 30, 10, 30]
ArrayDeque after removing elements: [10, 10, 10, 30]
```