# Java 中的 ArrayDeque remove()方法

> 原文：`https://www.geeksforgeeks.org/arraydeque-remove-method-in-java/`

## 1. `Java.util.ArrayDeque.remove()` 方法

`Java.util.ArrayDeque.remove()` 方法用于移除双端队列头部的元素。

**语法：**

```java
Array_Deque.remove()
```

**参数：** 该方法不取任何参数。

**返回值：** 这个方法返回出现在双端队列头部的元素。

**异常：** 如果双端队列为空，该方法抛出 `NoSuchElementException`。

下面的程序说明了 `Java.util.ArrayDeque.remove()` 方法：

**程序 1：**

```java
// Java code to illustrate remove()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[]) {
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

        // Removing elements using remove() method
        de_que.remove();
        de_que.remove();

        // Displaying the ArrayDeque after removal
        System.out.println("ArrayDeque after removing "
                           + "elements: " + de_que);
    }
}
```

**Output：**

```java
Initial ArrayDeque: [Welcome, To, Geeks, For, Geeks]
ArrayDeque after removing elements: [Geeks, For, Geeks]
```

**程序 2：**

```java
// Java code to illustrate remove()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[]) {
        // Creating an empty ArrayDeque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Use add() method to add elements into the Deque
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the ArrayDeque
        System.out.println("Initial ArrayDeque: " + de_que);

        // Removing elements using remove() method
        de_que.remove();
        de_que.remove();

        // Displaying the ArrayDeque after removal
        System.out.println("ArrayDeque after removing "
                           + "elements: " + de_que);
    }
}
```

**Output：**

```java
Initial ArrayDeque: [10, 15, 30, 20, 5]
ArrayDeque after removing elements: [30, 20, 5]
```

## 2. `Java.util.ArrayDeque.remove(Object)` 方法

`Java.util.ArrayDeque.remove(Object)` 方法用于从 `ArrayDeque` 中移除一个特定的元素。

**语法：**

```java
Priority_Queue.remove(Object O)
```

**参数：** 参数 `O` 属于数组类型，指定要从数组中删除的元素。

**返回值：** 如果指定的元素出现在双端队列中，该方法返回真，否则返回假。

下面的程序说明了 `Java.util.ArrayDeque.remove()` 方法：

**程序 1：**

```java
// Java code to illustrate remove()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[]) {
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

        // Removing elements using remove() method
        de_que.remove("Geeks");
        de_que.remove("For");
        de_que.remove("Welcome");

        // Displaying the ArrayDeque after removal
        System.out.println("ArrayDeque after removing "
                           + "elements: " + de_que);
    }
}
```

**Output：**

```java
Initial ArrayDeque: [Welcome, To, Geeks, For, Geeks]
ArrayDeque after removing elements: [To, Geeks]
```

**程序 2：**

```java
// Java code to illustrate remove()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[]) {
        // Creating an empty ArrayDeque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Use add() method to add elements into the Deque
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the ArrayDeque
        System.out.println("Initial ArrayDeque: " + de_que);

        // Removing elements using remove() method
        de_que.remove(30);
        de_que.remove(5);

        // Displaying the ArrayDeque after removal
        System.out.println("ArrayDeque after removing "
                           + "elements: " + de_que);
    }
}
```

**Output：**

```java
Initial ArrayDeque: [10, 15, 30, 20, 5]
ArrayDeque after removing elements: [10, 15, 20]
```