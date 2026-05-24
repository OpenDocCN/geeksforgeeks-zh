# Java 中的 ConcurrentHashMap containsKey()方法

> 原文: [https://www.geeksforgeeks.org/concurrenthashmap-containskey-method-in-java/](https://www.geeksforgeeks.org/concurrenthashmap-containskey-method-in-java/)

`java.util.concurrent.ConcurrentHashMap.containsKey()`方法是 Java 中的一个内置函数，它接受一个参数并检查它是否是这个映射中的一个键。

## 语法

```java
chm.containsKey(Object key_element)
```

## 参数

该方法接受对象类型的单个参数 `key_element`，检查其是否为键。

## 返回值

如果指定的 `key_element` 是该地图的一个键，则该方法返回 `true`，否则返回 `false`。

## 异常

当指定的 `key_element` 为空时，函数抛出 `NullPointerException`。

下面的程序举例说明了 `java.util.concurrent.ConcurrentHashMap.containsKey()` 方法的使用:

### 程序 1

该程序涉及将字符串值映射到整数键。

```java
/* Java Program Demonstrate containsKey()
   method of ConcurrentHashMap */

import java.util.concurrent.*;
class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {
        ConcurrentHashMap<Integer, String> chm =
                 new ConcurrentHashMap<Integer, String>();
        chm.put(100, "Geeks");
        chm.put(101, "for");
        chm.put(102, "Geeks");

// Checking whether 105 is a key of the map
        if (chm.containsKey(105)) {
            System.out.println("105 is a key.");
        }
        else {
            System.out.println("105 is not a key.");
        }

// Checking whether 100 is a key of the map
        if (chm.containsKey(100)) {
            System.out.println("100 is a key.");
        }
        else {
            System.out.println("100 is not a key.");
        }
    }
}
```

**输出:**

```java
105 is not a key.
100 is a key.
```

### 程序 2

该程序涉及将整数值映射到字符串键。

```java
/* Java Program Demonstrate containsKey()
   method of ConcurrentHashMap */

import java.util.concurrent.*;
class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {
        ConcurrentHashMap<String, Integer> chm = 
                  new ConcurrentHashMap<String, Integer>();
        chm.put("Geeks", 120);
        chm.put("for", 11);
        chm.put("GeeksforGeeks", 15);
        chm.put("Gfg", 50);
        chm.put("GFG", 25);

// Checking whether GFG is a key of the map
        if (chm.containsKey("GFG")) {
            System.out.println("GFG is a key.");
        }
        else {
            System.out.println("GFG is not a key.");
        }

// Checking whether Geek is a key of the map
        if (chm.containsKey("Geek")) {
            System.out.println("Geek is a key.");
        }
        else {
            System.out.println("Geek is not a key.");
        }
    }
}
```

**输出:**

```java
GFG is a key.
Geek is not a key.
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentHashMap.html#containsKey(java.lang.Object)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentHashMap.html#containsKey(java.lang.Object))