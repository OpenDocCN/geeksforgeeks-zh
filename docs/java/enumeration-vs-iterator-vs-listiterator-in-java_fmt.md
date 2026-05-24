# Java 中枚举器 vs 迭代器 vs 列表迭代器

> 原文：[https://www.geeksforgeks.org/enumeration-vs-iterator-vs-listiterator-in-java/](https://www.geeksforgeks.org/enumeration-vs-iterator-vs-listiterator-in-java/)

`Enumeration` 就是一个接口。它在 Java 的集合框架中用于逐个检索元素。`Enumeration` 是一个遗留接口，只适用于遗留类，如 `Vector`、`Hashtable`、`Stack` 等。它提供单向迭代。通过使用 `Enumeration`，我们只能执行读取操作，而不能执行移除操作。

`Enumeration` 对象可以通过调用 `Vector` 类中的 `elements()` 方法来创建。

```java
// Here "v" is a vector object. enum is of
// type Enumeration interface and refers to "v"
Enumeration enum = v.elements();
```

`Iterator` 是一个通用光标，可以应用于任何集合对象。它提供单向迭代。通过使用 `Iterator`，我们可以执行读取和移除操作，但是不能执行替换操作。每当我们想要枚举所有集合框架实现的接口中的元素时，比如 `Set`、`List`、`Queue`、`Deque`，以及 `Map` 接口的实现类，都必须使用 `Iterator`。

`Iterator` 对象可以通过调用集合接口中的 `iterator()` 方法来创建。

```java
// Here "c" is any collection object. itr is of
// type Iterator interface and refers to "c"
Iterator itr = c.iterator();
```

`ListIterator` 是三个光标中最强大的光标。`ListIterator` 只适用于 `ArrayList`、`LinkedList`、`Stack` 等列表实现的类。`ListIterator` 可以向前和向后遍历。通过使用 `ListIterator`，我们可以执行读取、移除和替换操作。当我们想要枚举列表的元素时，必须使用 `ListIterator`。

`ListIterator` 对象可以通过调用列表接口中的 `listIterator()` 方法来创建。

```java
// Here "l" is any list object. ltr is of
// type ListIterator interface and refers to "l"
ListIterator ltr = l.listIterator();
```

## Java 代码示例

```java
// A Java program to demonstrates the
// difference between Enumeration,
// Iterator, and ListIterator

import java.io.*;
import java.util.*;

class GFG {

    public static void main(String args[])
    {

        // Creating a vector object
        Vector<Integer> v = new Vector<Integer>();

        // Adding elements to the vector object
        v.add(10);
        v.add(20);
        v.add(30);
        v.add(40);
        v.add(50);

        System.out.println("Enumeration: ");

        // Creating an Enumeration object
        Enumeration e = v.elements();

        // Checking the next element availability
        while (e.hasMoreElements()) {

            // Moving cursor to the next element
            int i = (Integer)e.nextElement();

            // Printing the element
            System.out.print(i + " ");
        }
        System.out.println();
        System.out.println();

        System.out.println("Iterator: ");

        // Creating Iterator object
        Iterator<Integer> itr = v.iterator();

        // Checking the next element availability
        while (itr.hasNext()) {

            // Moving cursor to the next element
            int i = (Integer)itr.next();

            // Checking if i == 10 then
            // remove the element
            if (i == 10)
                itr.remove();
        }
        System.out.println(v);
        System.out.println();

        System.out.println("ListIterator: ");

        // Creating ListIterator object
        ListIterator<Integer> ltr = v.listIterator();

        // Checking the next element availability
        while (ltr.hasNext()) {

            // Moving cursor to the next element
            int i = (Integer)ltr.next();

            // Performing add, remove, and
            // replace operation
            if (i == 20)
                ltr.remove();

            else if (i == 30)
                ltr.add(60);

            else if (i == 40)
                ltr.set(100);
        }

        System.out.println(v);
    }
}
```

**输出**

```
Enumeration:
10 20 30 40 50

Iterator:
[20, 30, 40, 50]

ListIterator:
[30, 60, 100, 50]
```

## 显示 `Enumeration`、`Iterator` 和 `ListIterator` 之间差异的表格

| 属性 | `Enumeration` | `Iterator` | `ListIterator` |
| :--- | :--- | :--- | :--- |
| 1. 我们可以在哪里应用？ | 它只能应用于遗留类。 | 它可以应用于任何集合接口。 | 它可以应用于列表接口。 |
| 2. 是遗留的吗？ | 是（在 Java 1.0 中引入）。 | 否（在 Java 1.2 中引入）。 | 否（在 Java 1.2 中引入）。 |
| 3. 允许的移动方向 | 单向，即我们只能向前遍历集合中的元素。 | 单向，即我们只能向前遍历集合中的元素。 | 双向的，也就是说，我们可以向前和向后遍历集合中的元素。 |
| 4. 允许的操作 | 我们只能执行读取操作。 | 我们可以执行读取和移除操作。 | 我们可以执行读取、移除、添加和替换操作。 |
| 5. 我们怎样才能得到它？ | 通过调用 `Vector` 类中的 `elements()` 方法。 | 通过调用任何集合接口中存在的 `iterator()` 方法。 | 通过调用列表接口中的 `listIterator()` 方法。 |