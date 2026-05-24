# Java 中 ArrayBlockingQueue toArray()方法

> 原文: `https://www.geeksforgeeks.org/arrayblockingqueue-toarray-method-in-java/`

## 1. `ArrayBlockingQueue` 类的 `toArray()` 方法

`ArrayBlockingQueue` 类的 `toArray()` 方法用于创建一个包含与此 `ArrayBlockingQueue` 相同元素的数组，并保持正确的顺序。基本上，它将所有元素从 `ArrayBlockingQueue` 复制到一个新数组中。此方法充当数组和集合之间的桥梁。

**语法:**

```java
public Object[] toArray()
```

**返回值:** 该方法返回一个包含该队列中所有元素的数组。

下面的程序举例说明 `ArrayBlockingQueue` 类的 `toArray()` 方法:

**程序 1:**

```java
// Program Demonstrate how to apply toArray() method
// of ArrayBlockingQueue Class.

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {
    public static void main(String[] args) {
        // Define capacity of ArrayBlockingQueue
        int capacity = 5;

        // Create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> queue = new ArrayBlockingQueue<Integer>(capacity);

        // Add 5 elements to ArrayBlockingQueue
        queue.offer(423);
        queue.offer(422);
        queue.offer(421);
        queue.offer(420);
        queue.offer(424);

        // Create a array by calling toArray() method
        Object[] array = queue.toArray();

        // Print queue
        System.out.println("Queue is " + queue);

        // Print elements of array
        System.out.println("The array created by toArray() is:");
        for (Object i : array) {
            System.out.println(i);
        }
    }
}
```

**Output:**

```java
Queue is [423, 422, 421, 420, 424]
The array created by toArray() is:
423
422
421
420
424
```

**程序 2:**

```java
// Program Demonstrate how to apply toArray() method
// of ArrayBlockingQueue Class.

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {
    public static void main(String[] args) {
        // Define capacity of ArrayBlockingQueue
        int capacity = 5;

        // Create object of ArrayBlockingQueue
        ArrayBlockingQueue<String> queue = new ArrayBlockingQueue<String>(capacity);

        // Add 5 elements to ArrayBlockingQueue
        queue.offer("User");
        queue.offer("Employee");
        queue.offer("Manager");
        queue.offer("Analyst");
        queue.offer("HR");

        // Create a array by calling toArray() method
        Object[] array = queue.toArray();

        // Print queue
        System.out.println("Queue is " + queue);

        // Print elements of array
        System.out.println("The array created by toArray() is:");
        for (Object i : array) {
            System.out.println(i);
        }
    }
}
```

**Output:**

```java
Queue is [User, Employee, Manager, Analyst, HR]
The array created by toArray() is:
User
Employee
Manager
Analyst
HR
```

## 2. `ArrayBlockingQueue` 类的 `toArray(T[] arr)` 方法

`ArrayBlockingQueue` 类的 `toArray(T[] a)` 方法用于创建一个包含与此 `ArrayBlockingQueue` 相同元素的数组，并保持正确的顺序。它有一个附加条件。如果队列大小小于或等于指定数组，则返回数组的类型与参数中指定的数组相同。否则，将分配一个类型与指定数组相同的新数组，数组大小等于此队列的大小。此方法充当数组和集合之间的桥梁。
假设一个队列是一个 `ArrayBlockingQueue`，并且它只包含字符串。那么

```java
String[] new_arr = queue.toArray(new String[0]);
```

注意 `toArray(new Object[0])` 与 `toArray()` 方法相同。

**语法:**

```java
public T[] toArray(T[] a)
```

**参数:** 该方法取一个参数 `arr`，如果队列足够大，那么它是一个数组，队列的所有元素都将被复制到这个数组中；否则，会为此分配一个相同运行时类型的新数组。

**返回值:** 该方法返回一个包含该队列中所有元素的数组。

**异常:** 方法可以抛出以下异常之一:

*   `ArrayStoreException`: 传递的数组类型不同，无法与队列的元素进行比较时。
*   `NullPointerException`: 如果数组为空。

下面的程序说明了 `ArrayBlockingQueue` 类的 `Array(T[] a)` 方法:

**程序 1:**

```java
// Program Demonstrate how to apply toArray(T[] a) method
// of ArrayBlockingQueue Class.

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {
    public static void main(String[] args) {
        // Define capacity of ArrayBlockingQueue
        int capacity = 5;

        // Create object of ArrayBlockingQueue
        ArrayBlockingQueue<String> queue = new ArrayBlockingQueue<String>(capacity);

        // Add 5 elements to ArrayBlockingQueue
        queue.offer("User");
        queue.offer("Employee");
        queue.offer("Manager");
        queue.offer("Analyst");
        queue.offer("HR");

        // Creating the array
        String[] array = new String[5];

        // Calling toArray(T[] a) method
        Object[] ReturnArray = queue.toArray(array);

        // Print queue
        System.out.println("Queue is " + queue);

        // Print elements of array passed as parameter
        System.out.println();
        System.out.println("The array passed to toArray() is:");
        for (Object i : array) {
            System.out.println(i);
        }

        // Print elements of array retuned by method toArray()
        System.out.println();
        System.out.println("The array retuned by toArray() is:");
        for (Object i : ReturnArray) {
            System.out.println(i);
        }
    }
}
```

**Output:**

```java
Queue is [User, Employee, Manager, Analyst, HR]

The array passed to toArray() is:
User
Employee
Manager
Analyst
HR

The array retuned by toArray() is:
User
Employee
Manager
Analyst
HR
```

**参考:**

*   `https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ArrayBlockingQueue.html#toArray--`
*   `https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ArrayBlockingQueue.html#toArray-T:A-`