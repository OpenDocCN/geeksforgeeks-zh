# Java AbstractSequentialList的add()方法

> 原文：[https://www.geeksforgeeks.org/java-abstractsequentiallist-add/](https://www.geeksforgeeks.org/java-abstractsequentiallist-add/)

[`AbstractSequentialList`](https://www.geeksforgeeks.org/abstractsequentiallist-in-java-with-examples/) 使用 `List` 接口指定的 `add()` 方法，该方法在 `AbstractList` 类中被覆盖。因此，`AbstractSequentialList` 没有自己的 `add()` 方法。取而代之的是 `add(int index, E element)` 方法。

`AbstractSequentialList.add(int index, E element)` 方法将指定的元素插入到此列表的指定位置。它将当前在该位置的元素（如果有）和任何后续元素向右移动（将一个元素添加到它们的索引中）。此实现首先获取一个指向索引元素的列表迭代器（通过 `listIterator(index)`）。然后，它用 `ListIterator.add` 插入指定的元素。

因此，`add(E element)` 和 `add(int index, E element)` 都可以和 `AbstractSequentialList` 类一起使用。

## 语法

```java
public void add(int index, E element)
```

## 参数

该方法取两个参数：

*   `index` – 表示整数类型的索引，指定的元素将插入到该索引中。此参数是可选的。如果未指定，则指定的元素将插入列表中的最后一个位置。
*   `element` – 表示要插入列表的元素，类型为 `E`。

## 异常

该方法抛出以下异常：

*   `UnsupportedOperationException` – 如果此列表不支持添加操作。
*   `ClassCastException` – 如果指定元素的类别阻止其添加到此列表中。
*   `NullPointerException` – 如果指定的元素为空，并且该列表不允许空元素。
*   `IllegalArgumentException` – 如果指定元素的某些属性阻止其添加到此列表中。
*   `IndexOutOfBoundsException` – 如果索引超出范围 (`index < 0 || index > size()`)。

下面是说明 `add()` 方法的程序：

## 程序 1：添加元素，不通过索引

```java
// Java program to demonstrate
// add() method

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

        // Printing the list
        System.out.println(absl);
    }
}
```

### Output:

```java
[5, 6, 7]
```

## 程序 2：通过传递索引来添加元素

```java
// Java program to demonstrate
// add() method

import java.util.*;

public class GfG {

    public static void main(String[] args)
    {
        // Creating an instance of the AbstractSequentialList
        AbstractSequentialList<Integer> absl = new LinkedList<>();

        // adding elements to absl
        absl.add(0, 8);
        absl.add(1, 7);
        absl.add(1, 9);
        absl.add(3, 10);

        // Printing the list
        System.out.println(absl);
    }
}
```

### Output:

```java
[8, 9, 7, 10]
```

## 程序 3：演示 IndexOutOfBoundsException

```java
// Java code to show IndexOutOfBoundsException

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

        // Printing the list
        System.out.println(absl);

        try {
            // showing IndexOutOfBoundsException
            absl.add(10, 12);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

### Output:

```java
[5, 9, 6, 7, 10, 8, 7]
Exception: java.lang.IndexOutOfBoundsException: Index: 10, Size: 7
```

Java-collections 移除术语:Java-函数 Java-函数