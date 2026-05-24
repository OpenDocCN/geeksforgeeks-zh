# Java 中的 NavigableMap `higherKey()`方法

> 原文: [https://www.geeksforgeeks.org/navigablemap-higherkey-method-in-java/](https://www.geeksforgeeks.org/navigablemap-higherkey-method-in-java/)

`NavigableMap` 接口的 `higherKey()` 方法用于返回严格大于给定键的最小键，如果没有这样的键，则返回 `null`。

**语法:**
```java
public K higherKey(K key)
```

**参数:** 该方法以键 `key` 为参数。

**返回值:** 该方法返回大于键的最小键，或 `null` 如果没有这样的键。

**异常:** 如果指定的键为 `null`，并且该映射使用自然排序，或者其比较器不允许 `null` 键，则该方法抛出 `NullPointerException`。

以下是说明 `higherKey()` 方法的示例:

## 示例 1

```java
// Java program to demonstrate
// higherKey() method
// for <Integer, String>

import java.util.*;

public class GFG1 {
    public static void main(String[] args) throws Exception
    {
        try {
            // Creating object of NavigableMap
            NavigableMap<Integer, String>
                navmap = new TreeMap<Integer, String>();

            // Populating the map
            navmap.put(1, "One");
            navmap.put(2, "Two");
            navmap.put(3, "Three");
            navmap.put(4, "Four");
            navmap.put(5, "Five");

            // Printing the TreeMap
            System.out.println("NavigableMap: " + navmap);

            // Getting higher key value for 3
            // using higherKey() method
            int value = navmap.higherKey(3);

            // Printing the value
            System.out.println("The higherKey value "
                               + " for 3: " + value);
        }
        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**
```java
NavigableMap: {1=One, 2=Two, 3=Three, 4=Four, 5=Five}
The higherKey value  for 3: 4
```

## 示例 2: 适用于 `NullPointerException`

```java
// Java program to demonstrate
// higherKey() method
// for NullPointerException

import java.util.*;

public class GFG1 {
    public static void main(String[] args) throws Exception
    {
        try {
            // Creating object of TreeMap<Integer, String>
            NavigableMap<Integer, String>
                navmap = new TreeMap<Integer, String>();

            // Populating tree map
            navmap.put(1, "One");
            navmap.put(2, "Two");
            navmap.put(3, "Three");
            navmap.put(4, "Four");
            navmap.put(5, "Five");

            // Printing the NavigableMap
            System.out.println("TreeMap: " + navmap);

            // Getting higher key value for null
            // Using higherKey() method
            System.out.println("Trying to get higherKey"
                               + " value for null");

            int value = navmap.higherKey(null);

            // Printing the value
            System.out.println("Value is: " + value);
        }
        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**
```java
TreeMap: {1=One, 2=Two, 3=Three, 4=Four, 5=Five}
Trying to get higherKey value for null
Exception thrown : java.lang.NullPointerException
```