# 用 Java 将列表转换为集合

> 原文:[https://www.geeksforgeeks.org/convert-list-to-set-in-java/](https://www.geeksforgeeks.org/convert-list-to-set-in-java/)

Java Set 是 `java.util` 包的一部分，扩展了 `java.util.Collection` 接口。它不允许使用重复元素，最多只能容纳一个空元素。Java Set 接口的几个重要特性如下:

*   `Set` 接口是对象的无序集合，其中不能存储重复的值。
*   Java 集合不提供对元素插入或删除位置的控制。
*   基本上，`Set` 是由 `HashSet`、`LinkedHashSet` 或 `TreeSet`(排序表示)实现的。
*   `Set` 有各种 `add`、`clear`、`size` 等方法来增强这个界面的使用。

本文讨论了将一个[列表界面](https://www.geeksforgeeks.org/list-interface-java-examples/)转换为 Java 中的[集合的不同方法:](https://www.geeksforgeeks.org/set-in-java/)

## 1. Naive Approach

朴素的解决方案是创建一个空集合，并将指定列表的每个元素添加到新创建的集合中。

下面是朴素方法的实现:

```java
// Java Program to convert
// List to Set in Java 8

import java.util.*;
import java.util.stream.*;
import java.util.function.Function;

class GFG {

    // Generic function to convert list to set
    public static <T> Set<T> convertListToSet(List<T> list)
    {
        // create an empty set
        Set<T> set = new HashSet<>();

        // Add each element of list into the set
        for (T t : list)
            set.add(t);

        // return the set
        return set;
    }

    public static void main(String args[])
    {

        // Create a stream of integers
        List<String> list = Arrays.asList("GeeksForGeeks",
                                          "Geeks",
                                          "forGeeks",
                                          "A computer portal",
                                          "for",
                                          "Geeks");

        // Print the List
        System.out.println("List: " + list);

        // Convert List to stream
        Set<String> set = convertListToSet(list);

        // Print the Set
        System.out.println("Set from List: " + set);
    }
}
```

**输出:**

```java
List: [GeeksForGeeks, Geeks, forGeeks, A computer portal, for, Geeks]
Set from List: [Geeks, for, GeeksForGeeks, A computer portal, forGeeks]
```

## 2. Using Constructor

`HashSet` 构造函数可以接受另一个集合对象来构造一个包含指定列表元素的新集合。

下面是上述方法的实现:

```java
// Java Program to convert
// List to Set in Java 8

import java.util.*;
import java.util.stream.*;

class GFG {

    // Generic function to convert list to set
    public static <T> Set<T> convertListToSet(List<T> list)
    {
        // create a set from the List
        return new HashSet<>(list);
    }

    public static void main(String args[])
    {

        // Create a stream of integers
        List<String> list = Arrays.asList("GeeksForGeeks",
                                          "Geeks",
                                          "forGeeks",
                                          "A computer portal",
                                          "for",
                                          "Geeks");

        // Print the List
        System.out.println("List: " + list);

        // Convert List to stream
        Set<String> set = convertListToSet(list);

        // Print the Set
        System.out.println("Set from List: " + set);
    }
}
```

**输出:**

```java
List: [GeeksForGeeks, Geeks, forGeeks, A computer portal, for, Geeks]
Set from List: [Geeks, for, GeeksForGeeks, A computer portal, forGeeks]
```

## 3. Using Java 8 Stream API

`HashSet` 构造函数可以接受另一个集合对象来构造一个包含指定列表元素的新集合。

下面是上述方法的实现:

```java
// Java Program to convert
// List to Set in Java 8

import java.util.*;
import java.util.stream.*;

class GFG {

    // Generic function to convert list to set
    public static <T> Set<T> convertListToSet(List<T> list)
    {
        // create a set from the List
        return list.stream().collect(Collectors.toSet());
    }

    public static void main(String args[])
    {

        // Create a stream of integers
        List<String> list = Arrays.asList("GeeksForGeeks",
                                          "Geeks",
                                          "forGeeks",
                                          "A computer portal",
                                          "for",
                                          "Geeks");

        // Print the List
        System.out.println("List: " + list);

        // Convert List to stream
        Set<String> set = convertListToSet(list);

        // Print the Set
        System.out.println("Set from List: " + set);
    }
}
```

**输出:**

```java
List: [GeeksForGeeks, Geeks, forGeeks, A computer portal, for, Geeks]
Set from List: [Geeks, for, GeeksForGeeks, A computer portal, forGeeks]
```

## 4. Using Guava Sets.newHashSet()

`Sets.newHashSet()` 创建一个可变的 `HashSet` 实例，其中包含指定列表的元素。

下面是上述方法的实现:

```java
// Java Program to convert
// List to Set in Java 8

import java.util.*;
import java.util.stream.*;

class GFG {

    // Generic function to convert list to set
    public static <T> Set<T> convertListToSet(List<T> list)
    {
        // create a set from the List
        return Sets.newHashSet(list);
    }

    public static void main(String args[])
    {

        // Create a stream of integers
        List<String> list = Arrays.asList("GeeksForGeeks",
                                          "Geeks",
                                          "forGeeks",
                                          "A computer portal",
                                          "for",
                                          "Geeks");

        // Print the List
        System.out.println("List: " + list);

        // Convert List to stream
        Set<String> set = convertListToSet(list);

        // Print the Set
        System.out.println("Set from List: " + set);
    }
}
```

**输出:**

```java
List: [GeeksForGeeks, Geeks, forGeeks, A computer portal, for, Geeks]
Set from List: [Geeks, for, GeeksForGeeks, A computer portal, forGeeks]
```