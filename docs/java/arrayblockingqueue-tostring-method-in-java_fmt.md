# Java 中的 ArrayBlockingQueue toString()方法

> 原文：[https://www.geeksforgeeks.org/arrayblockingqueue-tostring-method-in-java/](https://www.geeksforgeeks.org/arrayblockingqueue-tostring-method-in-java/)

`ArrayBlockingQueue`类的`toString()`方法用于获取`ArrayBlockingQueue`对象的字符串表示。`ArrayBlockingQueue`的字符串包含从第一个（头）到最后一个（尾）顺序的元素，用方括号（“[]”）括起来。元素由字符“，”（逗号和空格）分隔。所以基本上`toString()`方法用于将`ArrayBlockingQueue`的所有元素转换成一个字符串。

## 语法

```java
public String toString()
```

## 返回值

该方法返回`ArrayBlockingQueue`的字符串表示形式。

## 程序示例

下面的程序说明了`ArrayBlockingQueue`类的`toString()`方法：

### 程序 1

```java
// Program to demonstrate how to apply toString() method
// of ArrayBlockingQueue Class.

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    public static void main(String[] args) {
        // Define capacity of ArrayBlockingQueue
        int capacity = 5;

        // Create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> queue = 
            new ArrayBlockingQueue<Integer>(capacity);

        // Add 5 elements to ArrayBlockingQueue
        queue.offer(423);
        queue.offer(422);
        queue.offer(421);
        queue.offer(420);
        queue.offer(424);

        // Print queue
        System.out.println("Queue is "+queue);

        // Call toString() method and Create an iterator
        String stringRepresentation=queue.toString();

        // Print String value returned by toString() method
        System.out.println("\nThe String returned by toString():");
        System.out.println(stringRepresentation);
    }
}
```

**输出：**

```java
Queue is [423, 422, 421, 420, 424]

The String returned by toString():
[423, 422, 421, 420, 424]
```

### 程序 2

```java
// Program Demonstrate how to apply toString() method
// of ArrayBlockingQueue Class.

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    public static void main(String[] args) {
        // Define capacity of ArrayBlockingQueue
        int capacity = 10;

        // Create object of ArrayBlockingQueue
        ArrayBlockingQueue<String> queue = 
            new ArrayBlockingQueue<String>(capacity);

        // Add 5 elements to ArrayBlockingQueue
        queue.offer("User");
        queue.offer("Employee");
        queue.offer("Manager");
        queue.offer("Analyst");
        queue.offer("HR");
        queue.offer("Tester");

        // Print queue
        System.out.println("Queue is "+queue);

        // Call toString() method and Create an iterator
        String stringRepresentation=queue.toString();

        // Print String value returned by toString() method
        System.out.println("\nThe String returned by toString():");
        System.out.println(stringRepresentation);
    }
}
```

**输出：**

```java
Queue is [User, Employee, Manager, Analyst, HR, Tester]

The String returned by toString():
[User, Employee, Manager, Analyst, HR, Tester]
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ArrayBlockingQueue.html#toString--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ArrayBlockingQueue.html#toString--)