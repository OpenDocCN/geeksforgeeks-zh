# 获取大于或小于指定值的树映射键、值或条目的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-get-treemap-key-value-or-entry-greater-or-less-than-the-specified-value/](https://www.geeksforgeeks.org/java-program-to-get-treemap-key-value-or-entry-greater-or-less-than-the-specified-value/)

`TreeMap` 类是一个红黑树实现。它帮助我们按照排序的顺序存储键值对。下面讨论 3 种方法，其中所有方法的树图中的 4 个键值对以及语法如下。

```java
tree.put(100, "=> Welcoming");
tree.put(120, "=> you to ");
tree.put(140, "=> computer science portal");
tree.put(200, "=> Geeks for Geeks");
```

## 方法 1：蛮力方法
蛮力方法只是为了存储 `TreeMap` 键值对并只显示。

### 示例

```java
// Java Program to Get TreeMap Key and Value

// Importing all classes
// of java.util package
import java.util.*;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Initialization of a TreeMap
        // using Generics
        TreeMap<Integer, String> tree
            = new TreeMap<Integer, String>();

        // Inserting the Elements into TreeMap
        tree.put(100, "=> Welcoming");
        tree.put(120, "=> you to ");
        tree.put(140, "=> computer science portal");
        tree.put(200, "=> Geeks for Geeks");

        // Iterating over TreeMap using for-each loop
        for (Map.Entry<Integer, String> map :
             tree.entrySet())

            // Displaying all entries-  keys and values
            // using getKey() and getValue() method
            System.out.println(map.getKey() + " "
                               + map.getValue());
    }
}
```

### 输出

```java
100 => Welcoming
120 => you to 
140 => computer science portal
200 => Geeks for Geeks
```

## 方法 2：使用内置函数
使用 `TreeMap` 类的内置函数：`higherKey()` 方法和 `lowerKey()` 方法打印大于或小于指定值的键。

`java.util.TreeMap` 类的 `higherKey()` 方法用于返回严格大于给定密钥的最小密钥，如果没有这样的密钥，则返回 `null`。

### 语法

```java
public K higherKey(K key)
```

### 参数
该方法以密钥 `k` 为参数。

### 返回值
该方法返回大于键的最小键，如果没有这样的键，则返回空。

### 异常
如果指定的键为空，并且此映射使用自然排序，或者其比较器不允许空键，则此方法引发 `NullPointerException`。

`lowerKey()` 方法用于返回严格小于给定键的最大键，作为参数传递。更简单地说，这个方法用于在作为参数传递的元素之后查找下一个最大的元素。

### 语法

```java
public K TreeMap.lowerKey(K key)
```

### 参数
该方法取一个强制参数键，即需要匹配的键。

### 返回值
此方法返回严格小于键的最大键，如果没有这样的键，则返回 `null`。

### 示例

```java
// Java Program to Get TreeMap Key, Value, then
// Entry Greater or Less than the Specified Value
// using lowerKey() and higherKey() of Tree class

// Importing all classes of
// java.util package
import java.util.*;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a TreeMap
        TreeMap<Integer, String> tree
            = new TreeMap<Integer, String>();

        // Inserting the Elements into TreeMap
        tree.put(100, "=> Welcoming");
        tree.put(120, "=> you to ");
        tree.put(140, "=> computer science portal");
        tree.put(200, "=> Geeks for Geeks");

        // Returning the smallest key among all the keys
        // greater than 150
        System.out.println("Smallest key among key > 150 : "
                           + tree.higherKey(150));

        // Returning the greatest key among all the keys
        // smaller than 150
        System.out.println("Greatest key among key < 150 : "
                           + tree.lowerKey(150));
    }
}
```

### 输出

```java
Smallest key among key > 150 : 200
Greatest key among key < 150 : 140
```

## 方法 3：使用 higherEntry().getValue() 和 lowerEntry().getValue()
通过 `higherEntry().getValue()` 打印大于或小于指定键的键对应的值。`higherEntry()` 方法的 `java.util.TreeMap` 类用于返回与严格大于给定键的最小键相关联的键值映射，如果没有这样的键，则返回 `null`，反之 `lowerEntry()` 方法的 `java.util.TreeMap` 类。

### 示例

```java
// Java Program to Get TreeMap Key, Value, or
// Entry Greater or Less than the Specified Value
// using higherEntry().getValue() function and
// lowerEntry().getValue()

// Importing all classes of
// java.util package
import java.util.*;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating a TreeMap
        TreeMap<Integer, String> tree
            = new TreeMap<Integer, String>();

        // Inserting the Elements into TreeMap
        tree.put(100, "=> Welcoming");
        tree.put(120, "=> you to ");
        tree.put(140, "=> computer science portal");
        tree.put(200, "=> Geeks for Geeks");

        // Returning the value corresponding to the key
        // which is smallest among the keys greater than 150
        System.out.println(
            tree.higherEntry(150).getValue());

        // Returning the value corresponding to the key
        // which is greatest among the keys smaller than 150
        System.out.println(tree.lowerEntry(150).getValue());
    }
}
```

### 输出

```java
=> Geeks for Geeks
=> computer science portal
```