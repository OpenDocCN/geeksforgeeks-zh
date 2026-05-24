# 如何在 Java 数组列表中的特定索引处添加元素？

> 原文：[https://www.geeksforgeeks.org/how-to-add-an-element-at-particular-index-in-java-arraylist/](https://www.geeksforgeeks.org/how-to-add-an-element-at-particular-index-in-java-arraylist/)

`ArrayList.add()` 方法用于在 Java ArrayList 的特定索引处添加元素。

## 语法

```java
public void add(int index, Object element) ;
```

## 参数

*   `index` - 必须插入元素的位置。索引从零开始。
*   `element` – 要在指定位置插入的元素。

## 异常

抛出 [`IndexOutOfBoundsException`](https://www.geeksforgeeks.org/understanding-array-indexoutofbounds-exception-in-java/)，该异常发生在试图访问分配的内存块中不存在的索引时。在 java 中，当访问负索引或内存空间索引时，会引发此异常。这里特别是当试图获取大于数组列表大小的索引或者在大于数组列表的 [`size()`](https://www.geeksforgeeks.org/list-size-method-in-java-with-examples/) 的索引处插入元素时。

## 示例

> **字符串列表**
>
> list = [A, B, C]
>
> `list.add(1, "D")`；
>
> `list.add(2, "E")`；
>
> list = [A, D, E, B, C]
>
> **整数列表**
>
> list = [1, 2, 3]
>
> `list.add(2, 4)`；
>
> list = [1, 2, 4, 3]

## 实施

```java
// Adding an Element at Particular
// Index in Java ArrayList
import java.io.*;
import java.util.ArrayList;

class GFG {

// Main driver method
    public static void main(String[] args)
    {
        // Creating an ArrayList
        ArrayList<String> list = new ArrayList<>();

// Adding elements to ArrayList
        // using add method for String ArrayList
        list.add("A");
        list.add("B");
        list.add("C");

/* Index is zero based */

// 3 gets added to the 1st position
        list.add(1, "D");

// 4 gets added to the 2nd(position)
        list.add(2, "E");

// Displaying elements in ArrayList
        System.out.println(list);
    }
}
```

## 输出

```java
[A, D, E, B, C]
```