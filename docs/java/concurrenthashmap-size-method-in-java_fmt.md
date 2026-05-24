# Java 中的 ConcurrentHashMap size() 方法

> 原文：[https://www.geeksforgeeks.org/concurrenthashmap-size-method-in-java/](https://www.geeksforgeeks.org/concurrenthashmap-size-method-in-java/)

`java.util.concurrent.ConcurrentHashMap.size()` 方法是 Java 中的一个内置函数，它计算该映射中键值映射的数量并返回整数值。

## 语法

```java
public int size()
```

## 返回值

该函数返回一个整数值，该值表示该映射中键值映射的数量。

## 示例

下面程序举例说明使用 `size()` 的方法：

### 程序 1

```java
// Java Program Demonstrate size()
// method of ConcurrentHashMap

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        ConcurrentHashMap<Integer, String>
            chm = new ConcurrentHashMap<Integer, String>();

        chm.put(100, "Geeks");
        chm.put(101, "for");
        chm.put(102, "Geeks");

        // Display the number of
        // key-value mappings
        System.out.println("The number of "
                           + "key-value mappings is "
                           + chm.size());
    }
}
```

**输出：**

```java
The number of key-value mappings is 3
```

### 程序 2

```java
// Java Program Demonstrate size()
// method of ConcurrentHashMap

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        ConcurrentHashMap<Integer, Integer>
            chm = new ConcurrentHashMap<Integer, Integer>();

        chm.put(1, 100);
        chm.put(2, 200);
        chm.put(3, 300);
        chm.put(4, 400);
        chm.put(5, 500);
        chm.put(6, 600);

        // Display the number of
        // key-value mappings
        System.out.println("The number of "
                           + "key-value mappings is "
                           + chm.size());
    }
}
```

**输出：**

```java
The number of key-value mappings is 6
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentHashMap.html#size()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentHashMap.html#size())