# Java 中的 NavigableMap pollFirstEntry()方法

> 原文：[https://www.geeksforgeeks.org/navigablemap-pollfirstentry-method-in-java/](https://www.geeksforgeeks.org/navigablemap-pollfirstentry-method-in-java/)

Java 中 [`NavigableMap` 接口](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)的 `pollFirstEntry()` 方法用于移除并返回与该映射中最少键相关联的键值映射，如果映射为空，则返回 `null`。

## 语法

```java
Map.Entry< K, V > pollFirstEntry()
```

其中，`K` 是该映射维护的键的类型，`V` 是映射到键的值的类型。

## 参数

本功能不接受任何参数。

## 返回值

从该映射中移除后，返回与最小键相关联的键值映射，如果映射为空，则返回空。

下面的程序说明了 Java 中的 `pollFirstEntry()` 方法：

## 程序 1：按键为整数时

```java
// Java code to demonstrate the working of
// pollFirstEntry() method

import java.io.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the NavigableMap of Integer and String
        NavigableMap<Integer, String> nmmp = new TreeMap<>();

        // assigning the values in the NavigableMap
        // using put()
        nmmp.put(2, "two");
        nmmp.put(7, "seven");
        nmmp.put(3, "three");

        System.out.println("First removed key-value from the map : "
                           + nmmp.pollFirstEntry());
    }
}
```

## 输出

```java
First removed key-value from the map : 2=two
```

## 程序 2：键为字符串时

```java
// Java code to demonstrate the working of
// pollFirstEntry() method

import java.io.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the NavigableMap of String and String
        NavigableMap<String, String> tmmp = new TreeMap<>();

        // assigning the values in the NavigableMap
        // using put()
        tmmp.put("one", "two");
        tmmp.put("six", "seven");
        tmmp.put("two", "three");

        System.out.println("First removed key-value from the map : "
                           + tmmp.pollFirstEntry());
    }
}
```

## 输出

```java
First removed key-value from the map : one=two
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/util/NavigableMap.html#pollFirstEntry()](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableMap.html#pollFirstEntry())