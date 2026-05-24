# Java 中的 ConcurrentLinkedQueue toArray()方法

> 原文: [https://www.geeksforgeeks.org/concurrentlinkedqueue-toarray-method-in-java/](https://www.geeksforgeeks.org/concurrentlinkedqueue-toarray-method-in-java/)

## 1. `toArray()`
`ConcurrentLinkedQueue` 的 `toArray()` 方法用于返回一个包含与 `ConcurrentLinkedQueue` 中相同元素且顺序正确的数组。基本上，它将所有元素从 `ConcurrentLinkedQueue` 复制到一个新数组中。此方法充当数组和 `ConcurrentLinkedQueue` 之间的桥梁。

**语法:**
```java
public Object[] toArray()
```

**返回:** 该方法返回一个数组，该数组包含类似于 `ConcurrentLinkedQueue` 的元素。

下面的程序说明了 `java.util.concurrentlinkedqueue.toArray()` 方法。

**例 1:**
```java
// Java Program Demonstrate toArray()
// method of ConcurrentLinkedQueue

import java.util.concurrent.ConcurrentLinkedQueue;

public class GFG {
    public static void main(String[] args) {
        // create object of ConcurrentLinkedQueue
        ConcurrentLinkedQueue<Integer> queue = new ConcurrentLinkedQueue<Integer>();

        // Add element to ConcurrentLinkedQueue
        queue.add(2300);
        queue.add(1322);
        queue.add(8945);
        queue.add(6512);

        // print queue details
        System.out.println("Queue Contains " + queue);

        // apply toArray() method on queue
        Object[] array = queue.toArray();

        // Print elements of array
        System.out.println("The array contains:");
        for (Object i : array) {
            System.out.print(i + "\t");
        }
    }
}
```

**Output:**
```java
Queue Contains [2300, 1322, 8945, 6512]
The array contains:
2300    1322    8945    6512
```

**例 2:**
```java
// Java Program Demonstrate toArray()
// method of ConcurrentLinkedQueue

import java.util.concurrent.ConcurrentLinkedQueue;

public class GFG {
    public static void main(String args[]) {
        // Creating a ConcurrentLinkedQueue
        ConcurrentLinkedQueue<String> queue = new ConcurrentLinkedQueue<String>();

        // elements into the Queue
        queue.add("Welcome");
        queue.add("To");
        queue.add("Jungle");

        // Displaying the ConcurrentLinkedQueue
        System.out.println("The ConcurrentLinkedQueue: " + queue);

        // Creating the array and using toArray()
        Object[] arr = queue.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**
```java
The ConcurrentLinkedQueue: [Welcome, To, Jungle]
The array is:
Welcome
To
Jungle
```

## 2. `toArray(T[] a)`
`ConcurrentLinkedQueue` 的 `toArray(T[] a)` 方法用于返回一个包含与该 `ConcurrentLinkedQueue` 中相同元素且顺序正确的数组。此方法与 `toArray()` 的区别仅在一个条件上。如果 `ConcurrentLinkedQueue` 的大小小于或等于传入的数组，则返回的数组类型与参数中传入的数组类型相同。否则，将分配一个与指定数组类型相同的新数组，其大小等于此队列的大小。此方法充当数组和集合之间的桥梁。

**语法:**
```java
public <T> T[] toArray(T[] a)
```

**参数:** 该方法以一个数组为参数，如果队列足够大，队列的所有元素都要复制到该参数中。否则，会为此分配一个相同运行时类型的新数组。

**返回:** 这个方法返回包含类似于 `ConcurrentLinkedQueue` 元素的数组。

**异常:** 该方法抛出以下异常:
*   `ArrayStoreException`: 当传递的数组与 `ConcurrentLinkedQueue` 的元素类型不同时。
*   `NullPointerException`: 如果传递的数组为空。

下面的程序说明了 `java.util.concurrentlinkedqueue.toArray(T[] a)` 方法。

**例 1:**
```java
// Java Program Demonstrate toArray()
// method of ConcurrentLinkedQueue

import java.util.concurrent.ConcurrentLinkedQueue;

public class GFG {
    public static void main(String[] args) {
        // create object of ConcurrentLinkedQueue
        ConcurrentLinkedQueue<String> queue = new ConcurrentLinkedQueue<String>();

        // elements into the Queue
        queue.add("Welcome");
        queue.add("To");
        queue.add("Jungle");

        // print queue details
        System.out.println("Queue Contains " + queue);

        // the array to pass in toArray()
        // array has size equal to size of ConcurrentLinkedQueue
        String[] passArray = new String[queue.size()];

        // Calling toArray(T[] a) method
        Object[] array = queue.toArray(passArray);

        // Print elements of passed array
        System.out.println("\nThe array passed :");
        for (String i : passArray) {
            System.out.print(i + " ");
        }

        System.out.println();

        // Print elements of returned array
        System.out.println("\nThe array returned :");
        for (Object i : array) {
            System.out.print(i + " ");
        }
    }
}
```

**Output:**
```java
Queue Contains [Welcome, To, Jungle]

The array passed :
Welcome To Jungle

The array returned :
Welcome To Jungle
```

**例 2:** 显示 `ArrayStoreException`
```java
// Java Program Demonstrate toArray()
// method of ConcurrentLinkedQueue

import java.util.concurrent.ConcurrentLinkedQueue;

public class GFG {
    public static void main(String[] args) {
        // create object of ConcurrentLinkedQueue
        ConcurrentLinkedQueue<Integer> queue = new ConcurrentLinkedQueue<Integer>();

        // Add element to ConcurrentLinkedQueue
        queue.add(2323);
        queue.add(2472);
        queue.add(4235);
        queue.add(1242);

        // the array to pass in toArray()
        // array has size equal to size of ConcurrentLinkedQueue
        String[] passArray = new String[queue.size()];

        // Calling toArray(T[] a) method
        try {
            Object[] array = queue.toArray(passArray);
        } catch (ArrayStoreException e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**
```java
Exception: java.lang.ArrayStoreException: java.lang.Integer
```

**示例 3:** 显示 `NullPointerException`
```java
// Java Program Demonstrate toArray()
// method of ConcurrentLinkedQueue

import java.util.concurrent.ConcurrentLinkedQueue;

public class GFG {
    public static void main(String[] args) {
        // create object of ConcurrentLinkedQueue
        ConcurrentLinkedQueue<Integer> queue = new ConcurrentLinkedQueue<Integer>();

        // Add element to ConcurrentLinkedQueue
        queue.add(2323);
        queue.add(2472);
        queue.add(4235);
        queue.add(1242);

        // the array to pass
        String[] passArray = null;

        // Calling toArray(T[] a) method
        try {
            Object[] array = queue.toArray(passArray);
        } catch (NullPointerException e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**
```java
Exception: java.lang.NullPointerException
```