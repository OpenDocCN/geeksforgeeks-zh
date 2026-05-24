# Java 中的 TreeMap 的 floorEntry() 和 floorKey() 方法

> 原文链接：https://www.geeksforgeeks.org/java-util-treemap-floor-java/

在许多场景中，找到小于给定值的最大值非常有用。在基于映射的容器中拥有这个特性总是一个好处。`java.util.TreeMap` 也通过 `floor()` 函数提供了这个功能。有两种变体，下面将讨论这两种变体。

## 1. floorEntry()

`floorEntry()` 方法返回与小于或等于给定键的最大键相关联的键值映射，如果没有这样的键，则返回 `null`。

```java
Parameters:
key : This is the key to be matched.
Return Value:
It returns an entry with the greatest key less than or equal to key,
or null if there is no such key.
Exception:
ClassCastException : This exception is thrown if the specified
key cannot be compared with the keys currently in the map.
NullPointerException : This exception is thrown if the specified
key is null and this map uses natural ordering, or its comparator does not permit null keys.
```

```java
// Java code to demonstrate the working
// of floorEntry()
import java.io.*;
import java.util.*;
public class floorEntry {
    public static void main(String[] args)
    {
        // Declaring the tree map of Integer and String
        TreeMap<Integer, String> tmp = new TreeMap<Integer, String>();

        // assigning the values in the tree map
        // using put()
        tmp.put(10, "ten");
        tmp.put(7, "seven");
        tmp.put(19, "nineteen");
        tmp.put(3, "three");

        // use of floorEntry()
        // displays the floor value of 6
        // prints 3=three
        System.out.println("The greatest key-value less than 6 is : "
        + tmp.floorEntry(6));
    }
}
```

输出:

```java
The greatest key-value less than 6 is : 3=three
```

## 2. floorKey()

`floorKey()` 方法返回小于或等于给定键的最大键，如果没有该键，则返回 `null`。

```java
Parameters:
key : This is the key to be matched.
Return Value:
It returns an entry with the greatest key less than or equal to key, or
null if there is no such key.
Exception:
ClassCastException : This exception is thrown if the specified
key cannot be compared with the keys currently in the map.
NullPointerException : This exception is thrown if the specified key
is null and this map uses natural ordering, or its comparator does not permit null keys.
```

```java
// Java code to demonstrate the working
// of floorKey()
import java.io.*;
import java.util.*;
public class floorKey {
    public static void main(String[] args)
    {
        // Declaring the tree map of Integer and String
        TreeMap<Integer, String> tmp = new TreeMap<Integer, String>();

        // assigning the values in the tree map
        // using put()
        tmp.put(10, "ten");
        tmp.put(7, "seven");
        tmp.put(19, "nineteen");
        tmp.put(3, "three");

        // use of floorKey()
        // displays the floor key of
        // prints 3
        System.out.println("The greatest key less than 6 is : "
        + tmp.floorKey(6));
    }
}
```

输出:

```java
The greatest key less than 6 is : 3
```

## 实际应用

该函数的可能应用是丰富的。从给定汽油或给定配料的可能菜肴的最大距离开始。前一个在下面的代码中讨论。

```java
// Java code to demonstrate the application
// of floorKey() and floorEntry
import java.io.*;
import java.util.*;
public class floorappli {
    public static void main(String[] args)
    {
        // Declaring the tree map of Integer and String
        TreeMap<Integer, String> destin = new TreeMap<Integer, String>();

        // assigning the km with destination
        // from beginning
        // using put()
        destin.put(10, "Delhi");
        destin.put(7, "Gurgaon");
        destin.put(19, "Noida");
        destin.put(3, "Ring Road");

        // Entering the available Petrol (consider 1km/litre)
        int petr = 12;

        // Maximum place you can reach
        System.out.println("The maximum place you can reach with given petrol : "
        + destin.floorEntry(petr));
    }
}
```

输出:

```java
The maximum place you can reach with given petrol : 10=Delhi
```