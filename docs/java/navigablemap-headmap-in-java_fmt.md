# Java 中的 NavigableMap.headMap()

> 原文: [https://www.geeksforgeeks.org/navigablemap-headmap-in-java/](https://www.geeksforgeeks.org/navigablemap-headmap-in-java/)

Java 中`NavigableMap`接口的`headMap()`方法用于返回此映射中键小于（或等于，如果`inclusive`为`true`）`toKey`的部分的视图。

*   返回的映射由此映射支持，因此返回映射中的更改将反映在此映射中，反之亦然。
*   返回的映射支持此映射支持的所有可选映射操作。
*   如果试图在返回的映射范围外插入一个键，它将抛出`IllegalArgumentException`。

## 语法

```java
NavigableMap<K, V> headMap(K toKey,
                          boolean inclusive)
```

其中，`K`是此映射维护的键的类型，`V`是与此映射中的键相关联的值。

## 参数

此方法接受两个参数：

*   `toKey`：此参数指的是结束键。
*   `inclusive`：此参数决定是否将结束键包含在视图中进行比较。

## 返回值

返回此映射中键小于（或等于，如果`inclusive`为`true`）`toKey`的部分的视图。

## 示例程序 1

当键为整数，且第二个参数缺失时。

```java
// Java code to demonstrate the working of
// headMap() method

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

        System.out.println("View of map with key less than"
                          + " or equal to 7 : " + nmmp.headMap(7));
    }
}
```

**输出:**

```java
View of map with key less than or equal to 7 : {2=two, 3=three}
```

## 示例程序 2

带第二个参数。

```java
// Java code to demonstrate the working of
// headMap() method

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
        nmmp.put(9, "nine");

        // headMap with second argument as true
        System.out.println("View of map with key less than"
                         + " or equal to 7 : " + nmmp.headMap(7, true));
    }
}
```

**输出:**

```java
View of map with key less than or equal to 7 : {2=two, 3=three, 7=seven}
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/util/NavigableMap.html#headMap(K, boolean)](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableMap.html#headMap(K, boolean))