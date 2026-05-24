# 用示例

在 Java 中抽象设置 `add()` 方法

> 原文: [https://www.geeksforgeks.org/abstractset-add-method-in-java-with-example/](https://www.geeksforgeks.org/abstractset-add-method-in-java-with-example/)

`AbstractSet` 类的 `add(E)` 方法将指定的元素追加到这个抽象集的末尾。

**语法:**

```java
boolean add(E element)
```

**参数:** 该函数接受单个参数 `element`，如上语法所示。此参数指定的元素被追加到抽象集的末尾。

**返回值:** 此方法成功执行后返回 `true`，否则 `false`。

**异常:** 此方法抛出:

*   `UnsupportedOperationException`: 如果此集合不支持添加操作。
*   `ClassCastException`: 如果指定元素的类阻止将其添加到此集合中。
*   `NullPointerException`: 如果指定的元素为空，并且此集合不允许空元素。
*   `IllegalArgumentException`: 如果元素的某些属性阻止它被添加到此集合中。
*   `IllegalStateException`: 如果由于插入限制此时无法添加元素。

下面的程序说明了 `java.util.AbstractSet.add(E element)` 方法的工作原理:

**例 1:**

```java
// Java code to illustrate boolean add(E element)
import java.util.*;

public class AbstractSetDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractSet
        AbstractSet<String> set
            = new TreeSet<String>();

        // Use add() method
        // to add elements in the AbstractSet
        set.add("Geeks");
        set.add("for");
        set.add("Geeks");
        set.add("10");
        set.add("20");

        // Output the present AbstractSet
        System.out.println("The AbstractSet is: "
                           + set);

        // Adding new elements to the end
        set.add("Last");
        set.add("Element");

        // Printing the new AbstractSet
        System.out.println("The new AbstractSet is: "
                           + set);
    }
}
```

**Output:**

```java
The AbstractSet is: [10, 20, Geeks, for]
The new AbstractSet is: [10, 20, Element, Geeks, Last, for]
```

**示例 2:** 演示空指针异常

```java
// Java code to illustrate
// boolean add(E element)

import java.util.*;

public class AbstractSetDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractSet
        AbstractSet<Integer> set
            = new TreeSet<Integer>();

        // Use add() method
        // to add elements in the AbstractSet
        set.add(10);
        set.add(20);
        set.add(30);
        set.add(40);
        set.add(50);

        // Output the present AbstractSet
        System.out.println("The AbstractSet is: "
                           + set);

        System.out.println("Trying to add null");

        try {
            // Adding null
            set.add(null);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
The AbstractSet is: [10, 20, 30, 40, 50]
Trying to add null
java.lang.NullPointerException
```