# Java AbstractSequentialList iterator()方法

> 原文：`https://www.geeksforgeeks.org/java-abstractsequentiallist-iterator-method/`

[`AbstractSequentialList`](https://www.geeksforgeeks.org/abstractsequentiallist-in-java-with-examples/)的`iterator()`方法在Java中用于获取列表上的迭代器或列表迭代器。它返回列表中元素的迭代器（按正确的顺序）。此方法覆盖类`AbstractList<E>`中的`iterator()`。

## 语法

```java
public Iterator<E> iterator()
```

## 返回值

此方法返回这个列表中元素的迭代器（按照正确的顺序）。

下面是演示`iterator()`方法的代码：

## 程序1

```java
// Java program to demonstrate
// iterator() method

import java.util.*;

public class GfG {

    public static void main(String[] args)
    {
        // Creating an instance of the AbstractSequentialList
        AbstractSequentialList<Integer> absl = new LinkedList<>();

        // adding elements to absl
        absl.add(5);
        absl.add(6);
        absl.add(7);
        absl.add(2, 8);
        absl.add(2, 7);
        absl.add(1, 9);
        absl.add(4, 10);

        // Getting Iterator
        Iterator<Integer> Itr = absl.iterator();

        // Traversing elements with help of iterator
        while (Itr.hasNext()) {
            System.out.print(Itr.next() + " ");
        }
    }
}
```

### 输出

```java
5 9 6 7 10 8 7
```

## 程序2

```java
// Java program to demonstrate
// iterator() method

import java.util.*;

public class GfG {

    public static void main(String[] args)
    {
        // Creating an instance of the AbstractSequentialList
        AbstractSequentialList<String> absl = new LinkedList<>();

        // adding elements to absl
        absl.add("Geeks");
        absl.add("ForGeeks");
        absl.add("A");
        absl.add("Portal");
        absl.add(3, "Computer Science");
        absl.add(5, "For Geeks");

        // Getting Iterator
        Iterator<String> Itr = absl.iterator();

        // Traversing elements with help of iterator
        while (Itr.hasNext()) {
            System.out.println(Itr.next());
        }
    }
}
```

### 输出

```java
Geeks
ForGeeks
A
Computer Science
Portal
For Geeks
```