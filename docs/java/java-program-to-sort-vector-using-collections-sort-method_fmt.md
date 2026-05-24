# 使用 `Collections.sort()` 方法对向量进行排序的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-sort-vector-using-collections-sort-method/](https://www.geeksforgeeks.org/java-program-to-sort-vector-using-collections-sort-method/)

`java.util.Collections.sort()` 方法存在于 `java.util.Collections` 类中。用于对集合的指定 [List](https://www.geeksforgeeks.org/list-interface-java-examples/) 中存在的元素进行升序排序。

## 语法

> `public static void sort(Vector<?> c);`

## 参数
作为参数的 `Vector` 实例。

## 图解
[`Collections.sort()` 方法](https://www.geeksforgeeks.org/collections-sort-java-examples/)

```
Let us suppose that our list contains
{"Geeks For Geeks", "Friends", "Dear", "Is", "Superb"}

After using Collection.sort(), we obtain a sorted list as
{"Dear", "Friends", "Geeks For Geeks", "Is", "Superb"}
```

1.  创建 `Vector` 实例。
2.  在向量中添加元素。
3.  调用方法前打印向量，以说明该方法的功能。
4.  使用 `Collections.sort()` 方法。
5.  排序后打印向量，可以看到排序是升序的。

## 示例 1

```java
// Java Program to Sort Vector
// using Collections.sort() Method

// Importing Collection and Vector class
import java.util.Collections;
import java.util.Vector;

public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Create a instance vector
        Vector<String> vec = new Vector<String>();

        // Insert the values in vector
        vec.add("a");
        vec.add("d");
        vec.add("e");
        vec.add("b");
        vec.add("c");

        // Display the vector
        System.out.println("original vector : " + vec);

        // Call sort() method
        Collections.sort(vec);

        // Display vector after replacing value
        System.out.println("\nsorted vector : " + vec);
    }
}
```

**Output**

```
original vector : [a, d, e, b, c]

sorted vector : [a, b, c, d, e]
```

## 示例 2

```java
// Java Program to Sort Vector
// using Collections.sort() Method

// Importing Collection and Vector class
import java.util.Collections;
import java.util.Vector;

public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Create a instance vector
        Vector<String> vec = new Vector<String>();

        // Insert the values in vector
        vec.add("4");
        vec.add("2");
        vec.add("7");
        vec.add("3");
        vec.add("2");

        // Display the vector
        System.out.println("\noriginal vector : " + vec);

        // Call sort() method
        Collections.sort(vec);

        // Display vector after replacing value
        System.out.println("\nsorted vector : " + vec);
    }
}
```

**Output**

```
original vector : [4, 2, 7, 3, 2]

sorted vector : [2, 2, 3, 4, 7]
```