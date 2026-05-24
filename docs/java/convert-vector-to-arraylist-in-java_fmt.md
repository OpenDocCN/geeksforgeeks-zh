# 将向量转换为 Java 中的数组列表

> 原文：`https://www.geeksforgeeks.org/convert-vector-to-arraylist-in-java/`

有多种方法可以将向量转换为数组列表，使用在数组列表构造函数中传递向量，以及使用简单的向量遍历和向数组列表添加值。

## 方法 1

1.  创建一个 `Vector`。
2.  向 `Vector` 添加一些值。
3.  创建一个新的数组列表。
4.  从左到右遍历该向量。
5.  开始将每个元素添加到数组列表中。

下面是上述方法的实现：

```java
// Java program to Convert Vector to ArrayList in Java
import java.util.Vector;
import java.util.ArrayList;

public class GFG {
    public static void main(String[] args)
    {
        // Create a Vector that contain strings
        Vector<String> v = new Vector<String>();

        // add values in vector
        v.add("a");
        v.add("b");
        v.add("c");
        v.add("d");
        v.add("e");

        // Display the Vector
        System.out.println(" Vector :  " + v);

        // Create a new ArrayList
        ArrayList<String> al = new ArrayList<String>();

        // Traverse the vector and add elements to ArrayList
        for (String s : v)
            al.add(s);

        // Display ArrayList
        System.out.println("\n ArrayList : " + al);
    }
}
```

**输出：**

```
 Vector :  [a, b, c, d, e]

 ArrayList : [a, b, c, d, e]
```

**时间复杂度:** `O(n)`

## 方法 2

*   创建一个 `Vector`。
*   向 `Vector` 添加一些值。
*   创建一个数组列表并在数组列表构造函数中传递该向量。

**语法:**

```java
ArrayList<String> ArrList = new ArrayList<String>(vector);
```

下面是上述方法的实现：

```java
// Convert Vector to ArrayList in Java
import java.util.Vector;
import java.util.ArrayList;

public class GFG {

    public static void main(String[] args)
    {

        // Create a Vector that contain strings
        Vector<String> v = new Vector<String>();

        // add values in vector
        v.add("a");
        v.add("b");
        v.add("c");
        v.add("d");
        v.add("e");

        // Display the Vector
        System.out.println(" Vector :  " + v);

        // Convert Vector to ArrayList
        ArrayList<String> Arrlist
            = new ArrayList<String>(v);

        // Display ArrayList
        System.out.println("\n ArrayList : " + Arrlist);
    }
}
```

**输出：**

```
 Vector :  [a, b, c, d, e]

 ArrayList : [a, b, c, d, e]
```

**时间复杂度:** `O(n)`