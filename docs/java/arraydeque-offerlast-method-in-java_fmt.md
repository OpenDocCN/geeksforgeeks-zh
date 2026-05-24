# Java中的ArrayDeque offerLast()方法

> 原文：[`https://www.geeksforgeeks.org/arraydeque-offerlast-method-in-java/`](https://www.geeksforgeeks.org/arraydeque-offerlast-method-in-java/)

Java中的`java.util.ArrayDeque.offerLast(Object element)`方法用于在这个Deque的末尾添加一个特定的元素。功能类似于Java中`ArrayDeque`的[`addLast()`](https://www.geeksforgeeks.org/arraydeque-addlast-method-in-java/)、[`add()`](https://www.geeksforgeeks.org/arraydeque-add-method-in-java/)和`offer()`方法。

## 语法

```java
Array_Deque.offerLast(Object element)
```

## 参数
参数`element`的类型为`ArrayDeque`，指的是要在Deque末尾添加的元素。

## 返回值
如果元素被成功添加到deque中，函数返回`true`，否则返回`false`。

## 异常
如果传递的参数为空，该方法将抛出`NullPointerException`。

下面的程序说明了`java.util.ArrayDeque.offerLast()`方法：

### 程序1：将字符串元素添加到Deque中

```java
// Java code to illustrate offerLast()
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
        System.out.println("Initial Deque: " + de_que);

        // Using offerLast() to add elements
        de_que.offerLast("Hello");
        de_que.offerLast("World");

        // Displaying the ArrayDeque
        System.out.println("Final Deque: " + de_que);
    }
}
```

**Output:**

```java
Initial Deque: [Welcome, To, Geeks, 4, Geeks]
Final Deque: [Welcome, To, Geeks, 4, Geeks, Hello, World]
```

### 程序2：将整数元素加入到Deque中

```java
// Java code to illustrate offerLast()
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
        System.out.println("Initial Deque: " + de_que);

        // Using offerLast() to add elements
        de_que.offerLast(1658);
        de_que.offerLast(2458);

        // Displaying the ArrayDeque
        System.out.println("Final Deque: " + de_que);
    }
}
```

**Output:**

```java
Initial Deque: [10, 15, 30, 20, 5]
Final Deque: [10, 15, 30, 20, 5, 1658, 2458]
```