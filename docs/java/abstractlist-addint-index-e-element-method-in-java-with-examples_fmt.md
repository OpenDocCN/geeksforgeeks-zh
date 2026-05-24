# Java 中 AbstractList 的 add(int index, E element) 方法示例

> 原文：[https://www.geeksforgeeks.org/abstractlist-addint-index-e-element-method-in-java-with-examples/](https://www.geeksforgeeks.org/abstractlist-addint-index-e-element-method-in-java-with-examples/)

[`AbstractList`](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/) 的 `add(int index, E element)` 方法用于在该列表的指定位置插入一个元素。新元素被插入到列表中的指定索引处。

**语法：**
```java
public void add(int index, E element)
```

**参数：** 该方法取 2 个参数：
1.  `index`：指定要插入元素的索引。
2.  `element`：要插入的元素。

**返回：** 如果元素成功插入列表，函数返回布尔值 `true`，否则返回 `false`。

**异常：** 出现的异常有：
*   `ClassCastException`：如果此集合中某个元素的类与指定集合不兼容。
*   `NullPointerException`：如果此集合包含 `null` 元素且指定集合不允许 `null` 元素，或者指定集合为 `null`。
*   `UnsupportedOperationException`：如果列表不支持添加操作。
*   `IllegalArgumentException`：如果指定元素的某些属性阻止其被添加到此列表中。
*   `IndexOutOfBoundsException`：如果索引超出范围 (`index < 0 || index > size()`)。

下面的程序说明了 `AbstractList` 类的 `add(int index, E element)` 函数：

**程序 1：**
```java
// Java code to illustrate AbstractList
// add(int index, int position) method

import java.io.*;
import java.util.*;

public class ArrayListDemo {
    public static void main(String[] args)
    {

        // Create an empty list
        // with an initial capacity
        AbstractList<Integer> list
            = new ArrayList<Integer>(5);

        // Use add() method
        // to add elements in the list
        list.add(3);
        list.add(6);
        list.add(9);
        list.add(12);

        // Prints all the elements
        // available in list
        System.out.println("Before: "
                           + list);

        // Add(int index, int element) method
        list.add(1, 4);

        // Prints all the elements
        // after the above method
        System.out.println("After: "
                           + list);
    }
}
```

**输出：**
```java
Before: [3, 6, 9, 12]
After: [3, 4, 6, 9, 12]
```

**程序 2：**
```java
// Java code to illustrate AbstractList
// add(int index, int position) method

import java.io.*;
import java.util.*;

public class ArrayListDemo {
    public static void main(String[] args)
    {

        // Create an empty list
        // with an initial capacity
        AbstractList<String> list
            = new ArrayList<String>(5);

        // Use add() method
        // to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Computer");
        list.add("Portal");

        // Prints all the elements
        // available in the list
        System.out.println("Before: " + list);

        // Add(int index, int element) method
        list.add(2, "Geeks");

        // Prints all the elements
        // after the above method
        System.out.println("After: " + list);
    }
}
```

**输出：**
```java
Before: [Geeks, for, Computer, Portal]
After: [Geeks, for, Geeks, Computer, Portal]
```

**参考：** [`https://docs.oracle.com/javase/7/docs/api/java/util/AbstractList.html#add(int, %20E)`](https://docs.oracle.com/javase/7/docs/api/java/util/AbstractList.html#add(int, %20E))