# Java 中的集合 `add()` 方法，带示例

> 原文: [https://www.geeksforgeeks.org/collection-add-method-in-java-with-examples/](https://www.geeksforgeeks.org/collection-add-method-in-java-with-examples/)

`java.util.Collection` 接口的 `add(E element)` 方法用于将元素 `element` 添加到该集合中。此方法返回一个描述操作成功与否的布尔值。如果添加了元素，它将返回 `true`，否则将返回 `false`。

## 语法

```java
Collection.add(E element)
```

## 参数

该方法接受一个强制参数 `element`，类型为 `E`，将被添加到该集合中。

## 返回值

一个布尔值描述操作的成功。如果添加了元素，它将返回 `true`，否则将返回 `false`。

## 异常

如果此集合不支持添加操作，该方法将抛出以下异常：

*   **`ClassCastException`**: 如果指定元素的类阻止其被添加到此集合中。
*   **`NullPointerException`**: 如果指定元素为空且此集合不允许空元素。
*   **`IllegalStateException`**: 如果由于插入限制，此时无法添加该元素。

现在我们将在不同的类上实现这个方法，因为当涉及到 Java 编程时，它是一个非常重要和必要的方法，所以这里我们将对每个类强调如下：

*   `LinkedList` 类
*   `ArrayDeque` 类
*   `ArrayList` 类
*   `NullPointerException` 被抛出的情况

让我们通过干净的 Java 示例在上面列出的所有 4 种情况下实现 `add()` 方法，如下所示：

### 示例 1: `LinkedList` 类

```java
// Java code to illustrate boolean add() method

import java.io.*;
import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        // creating an empty LinkedList
        Collection<String> list = new LinkedList<String>();

        // use add() method to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");

        // Output the present list
        System.out.println("The list is: " + list);

        // Adding new elements to the end
        list.add("Last");
        list.add("Element");

        // printing the new list
        System.out.println("The new List is: " + list);
    }
}
```

**输出:**

```java
The list is: [Geeks, for, Geeks]
The new List is: [Geeks, for, Geeks, Last, Element]
```

### 示例 2: `ArrayDeque` 类

```java
// Java code to illustrate add() method

import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Collection<String> de_que = new ArrayDeque<String>();

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

**输出:**

```java
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
```

### 示例 3: 使用 `ArrayList` 类

```java
// Java code to illustrate add() method

import java.io.*;
import java.util.*;

public class ArrayListDemo {
    public static void main(String[] args)
    {
        // create an empty array list with an initial capacity
        Collection<Integer> arrlist = new ArrayList<Integer>(5);

        // use add() method to add elements in the list
        arrlist.add(15);
        arrlist.add(20);
        arrlist.add(25);

        // prints all the elements available in list
        for (Integer number : arrlist) {
            System.out.println("Number = " + number);
        }
    }
}
```

**输出:**

```java
Number = 15
Number = 20
Number = 25
```

> 注意：`GeeksforGeeks` 保持了一个绑定，在特殊情况下会抛出 `NullPointerException`，如下例所示:

### 示例 4: `NullPointerException` 被抛出的情况

```java
// Java code to illustrate boolean add()
// Where NullPointerException is Thrown

// Importing required utility classes
import java.util.*;

// Main class
// LinkedListDemo
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an empty ArrayList of string type
        Collection<String> list = new ArrayList<String>();

        // Printing and displaying the Arraylist
        System.out.println("The ArrayList is: " + list);

        // Note: Here by now we have not added any element/s

        // Try block to check for exceptions
        try {
            // Appending the null to the list
            // using add() method
            list.add(null);
        }

        // Catch block to handle exceptions
        catch (Exception e) {
            // Display message when exceptions occurs
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
The ArrayList is: []
```

**输出说明:** 这里我们需要注意到，因为我们只会收到一个 `List`。因此，最好记录 `add()` 方法是否接受 `null` 取决于它是否需要支持 `null`。