# Java 中的 `Collections.fill()` 方法示例

> 原文：[https://www.geeksforgeeks.org/collections-fill-method-in-java-with-examples/](https://www.geeksforgeeks.org/collections-fill-method-in-java-with-examples/)

`java.util.Collections` 类的 `fill()` 方法用于用指定的元素替换指定列表的所有元素。

该方法在线性时间内运行。

## 语法

```java
public static <T> void fill(List<? super T> list, T obj)
```

## 参数

该方法以下列参数为参数：

*   `list` – 要用指定元素填充的列表。
*   `obj` – 填充指定列表的元素。

以下是说明 `fill()` 方法的示例。

## 示例 1

```java
// Java program to demonstrate
// fill() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        // creating object of List<Integer>
        List<String> arrlist = new ArrayList<String>();

        // Adding element to srclst
        arrlist.add("A");
        arrlist.add("B");
        arrlist.add("C");

        // print the elements
        System.out.println("List elements before fill: "
                           + arrlist);

        // fill the list
        Collections.fill(arrlist, "TAJMAHAL");

        // print the elements
        System.out.println("\nList elements after fill: "
                           + arrlist);
    }
}
```

**输出：**

```java
List elements before fill: [A, B, C]

List elements after fill: [TAJMAHAL, TAJMAHAL, TAJMAHAL]
```

## 示例 2

```java
// Java program to demonstrate
// fill() method
// for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        // creating object of List<Integer>
        List<Integer> arrlist = new ArrayList<Integer>();

        // Adding element to srclst
        arrlist.add(20);
        arrlist.add(30);
        arrlist.add(40);

        // print the elements
        System.out.println("List elements before fill: "
                           + arrlist);

        // fill the list
        Collections.fill(arrlist, 500);

        // print the elements
        System.out.println("\nList elements after fill: "
                           + arrlist);
    }
}
```

**输出：**

```java
List elements before fill: [20, 30, 40]

List elements after fill: [500, 500, 500]
```