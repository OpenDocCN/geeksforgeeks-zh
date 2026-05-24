# 如何避免 Java 中的 ConcurrentModificationException？

> 原文：[https://www.geeksforgeeks.org/how-to-avoid-concurrentmodificationexception-in-java/](https://www.geeksforgeeks.org/how-to-avoid-concurrentmodificationexception-in-java/)

[`ConcurrentModificationException`](https://www.geeksforgeeks.org/concurrentmodificationexception-in-java-with-examples/) 是 Java 中预定义的异常，它在我们使用 Java Collections 时发生，即每当我们试图在未经许可的情况下并发修改一个对象时，`ConcurrentModificationException` 就会发生，它存在于 `java.util` 包中。

## 过程

为了避免在单线程环境中出现这种异常，需要一些步骤。它们如下：

*   我们可以迭代数组，而不是迭代集合类。这对于较小的列表来说非常好，那么较大的列表呢？非常基本的一点是，我们知道如果数组大小很大，就会影响性能。因此，这种方法只对较小尺寸的数组有效。
*   下一个方法是 **Synchronized block 方法**，这里我们实际上是将列表锁定在一个 `Synchronized` block 中以避免异常。很酷吧？但是猜猜这也不是避免异常的有效方法为什么？因为没有使用多线程的目的。
*   更好的方法是我们有 [`ConcurrentHashMap`](https://www.geeksforgeeks.org/concurrenthashmap-in-java/) 和 `CopyOnWriteArrayList`，这是上述方法中最好的。

## 方法

这里提出了两种方法，从最简单的方法开始，到达到目标的最佳方法结束。

1.  **使用循环**：我们使用了 `Iterator remove()` 方法，而不是我们可以使用 `for` 循环来避免单线程环境中的 `ConcurrentModificationException`。如果我们添加任何额外的对象，那么我们可以确保我们的代码能够处理它们。
2.  **使用 remove() 方法**：我们可以使用 `remove` 方法从集合中移除对象。这里有一个问题，那就是您只能从列表中删除同一个对象，而不能删除任何其他对象。

### 例 1

```java
// Java Program to Avoid
// AvoidConcurrentModificationException

// Importing Map and List utility classes
//  from java.util package
import java.util.List;
import java.util.Map;

// Importing classes from java.util.concurrent package
import java.util.concurrent.ConcurrentHashMap;
import java.util.concurrent.CopyOnWriteArrayList;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of List class
        // Declaring object of string type
        List<String> marvel
            = new CopyOnWriteArrayList<String>();

        // Adding elements to the above object created
        // Custom input entries
        marvel.add("IronMan");
        marvel.add("BlackWidow");
        marvel.add("Hulk");
        marvel.add("DoctorStrange");
        marvel.add("SpiderMan");

        // Iterating over object created using size() method
        for (int i = 0; i < marvel.size(); i++) {

            // Print and display the object elements
            // using get() method
            System.out.println("Avenger : "
                               + marvel.get(i));

            // Condition check over object elements

            // If specific element is matched
            if (marvel.get(i).equals("BlackWidow")) {

                marvel.remove(i);
                i--;

                // Add this specific element
                marvel.add("CaptianAmerica");
            }
        }

        // Now getting the final total size by checking
        // how many elements are there inside object
        System.out.println("Total Avengers : "
                           + marvel.size());
    }
}
```

**Output**

```java
Avenger : IronMan
Avenger : BlackWidow
Avenger : Hulk
Avenger : DoctorStrange
Avenger : SpiderMan
Avenger : CaptianAmerica
Total Avengers :5
```

> **注意**：如果我们尝试用子列表修改原列表的结构，也会出现异常。下面是同样的例子。

### 例 2

```java
// Java Program to Illustrate ConcurrentModificationException
// WithArrayListSubList

// Importing List and Arraylist classes utility classes
// from java.util package
import java.util.ArrayList;
import java.util.List;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args) {

        // Creating a List class object
        // Declaring object of string type
        List <String> names = new ArrayList <>();

        // Adding elements to the object of List class

        // Custom input entries
        names.add("Java");
        names.add("C++");
        names.add("Phython");
        names.add("JavaScript");

        List < String > first2Names = names.subList(0, 2);

        System.out.println(names + " , " + first2Names);

        names.set(1, "Ruby");

        // check the output below. 🙂
        System.out.println(names + " , " + first2Names);

        // Now we add another string to
        // get ConcurrentModificationException
        names.add("SQL");

        // This line throws an exception
        System.out.println(names + " , " + first2Names);

    }
}
```