# 如何在 Java 中从向量中获取第一个和最后一个元素？

> 原文: [https://www.geeksforgeeks.org/how-to-get-first-and-last-element-from-the-vector-in-java/](https://www.geeksforgeeks.org/how-to-get-first-and-last-element-from-the-vector-in-java/)

向量中的第一个元素可以使用表示 `util` 包的 `Vector` 类的 `firstElement()` 方法获得。向量中的最后一个元素可以使用 `Vector` 类的 `lastElement()` 方法获得，该方法也代表 `util` 包。这两种方法都不需要任何参数。

## 可以通过两种方式提取向量的第一个和最后一个元素：

1.  通过 `get()` 方法直接获取索引 0 和索引 `size-1` 处的元素。
2.  使用 `firstElement()` 和 `lastElement()` 方法。

### 方法 1: 获取第 0 个和最后一个索引的元素

我们可以使用 `get()` 方法：

*   对于第一个元素，获取索引 0 处的元素。
*   对于最后一个元素，获取索引为 `(vector.size() - 1)` 处的元素。

```java
// Java program to get the first and
// last element of vector

import java.util.Vector;

public class Example {

    public static void main(String args[]) {

        // Create instance of Vector class.
        Vector<Integer> vector = new Vector<>();

        // Add some Element in Vector
        vector.add(5);
        vector.add(9);
        vector.add(0);
        vector.add(5);
        vector.add(3);

        System.out.println("The Vector Elements are: " + vector);

        System.out.println(
            "The First Element of the Vector is : " + vector.get(0));

        System.out.println(
            "The Last Element of the Vector is : " + vector.get(vector.size() - 1));
    }
}
```

**输出**

```java
The Vector Elements are: [5, 9, 0, 5, 3]
The First Element of the Vector is : 5
The Last Element of the Vector is : 3
```