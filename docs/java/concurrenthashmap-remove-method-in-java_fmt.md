# Java 中的 ConcurrentHashMap `remove()` 方法

> 原文: [https://www.geeksforgeeks.org/concurrenthashmap-remove-method-in-java/](https://www.geeksforgeeks.org/concurrenthashmap-remove-method-in-java/)

## `remove(Object key)`

Java 中 `ConcurrentHashMap` 类的 `remove(Object key)` 方法用于从映射中移除指定的键值对。如果该键在映射中不存在，则该方法不执行任何操作。

### 语法

```java
public V remove(Object key)
```

### 参数

此方法接受一个强制参数 `key`，即需要移除的键。

### 返回值

此方法返回与键 `key` 关联的先前值，如果该键没有映射关系，则返回 `null`。

### 异常

如果指定的键为 `null`，此方法会抛出 `NullPointerException`。

下面是说明 `remove()` 方法的程序：

## 程序一：基本用法

```java
// Java program to demonstrate remove() method

import java.util.*;
import java.util.concurrent.ConcurrentHashMap;

public class ConcurrentHashMapExample {

    public static void main(String[] args)
    {
        // Creating ConcurrentHashMap
        Map<String, String> my_cmmap
            = new ConcurrentHashMap<String, String>();

        // Adding elements to the map
        // using put() method
        my_cmmap.put("1", "1");
        my_cmmap.put("2", "1");
        my_cmmap.put("3", "1");
        my_cmmap.put("4", "1");
        my_cmmap.put("5", "1");
        my_cmmap.put("6", "1");

        // Printing the map
        System.out.println("Map: " + my_cmmap);
        System.out.println();

        // Removing the mapping
        // with existing key 6
        // using remove() method
        String valueRemoved = my_cmmap.remove("6");

        // Printing the map after remove()
        System.out.println(
            "After removing mapping with key 6:");
        System.out.println("Map: " + my_cmmap);
        System.out.println("Value removed: "
                           + valueRemoved);
        System.out.println();

        // Removing the mapping
        // with non-existing key 10
        // using remove() method
        valueRemoved = my_cmmap.remove("10");

        // Printing the map after remove()
        System.out.println(
            "After removing mapping with key 10:");
        System.out.println("Map: " + my_cmmap);
        System.out.println("Value removed: "
                           + valueRemoved);
    }
}
```

### 输出

```
Map: {1=1, 2=1, 3=1, 4=1, 5=1, 6=1}

After removing mapping with key 6:
Map: {1=1, 2=1, 3=1, 4=1, 5=1}
Value removed: 1

After removing mapping with key 10:
Map: {1=1, 2=1, 3=1, 4=1, 5=1}
Value removed: null
```

## 程序二：演示 `NullPointerException`

```java
// Java program to demonstrate remove() method

import java.util.*;
import java.util.concurrent.ConcurrentHashMap;

public class ConcurrentHashMapExample {

    public static void main(String[] args)
    {
        // Creating ConcurrentHashMap
        Map<String, String> my_cmmap
            = new ConcurrentHashMap<String, String>();

        // Adding elements to the map
        // using put() method
        my_cmmap.put("1", "1");
        my_cmmap.put("2", "1");
        my_cmmap.put("3", "1");
        my_cmmap.put("4", "1");
        my_cmmap.put("5", "1");
        my_cmmap.put("6", "1");

        // Printing the map
        System.out.println("Map: " + my_cmmap);
        System.out.println();

        try {
            // Removing the mapping with null key
            // using remove() method
            my_cmmap.remove(null);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

### 输出

```
Map: {1=1, 2=1, 3=1, 4=1, 5=1, 6=1}

Exception: java.lang.NullPointerException
```