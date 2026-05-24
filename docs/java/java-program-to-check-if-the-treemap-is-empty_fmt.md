# 检查TreeMap是否为空

> 原文：[https://www.geeksforgeeks.org/java-program-to-check-if-the-treemap-is-empty/](https://www.geeksforgeeks.org/java-program-to-check-if-the-treemap-is-empty/)

Java 中的 `TreeMap` 与 `AbstractMap` 类一起用于实现 `Map` 接口和 `NavigableMap` 接口。`TreeMap` 根据其键的自然顺序进行排序，或者通过 `TreeMap` 创建时提供的 `Comparator` 进行排序，具体取决于使用的构造函数。

## 方法

1.  使用 `isEmpty()` 方法。
2.  使用 `size()` 方法。

## 方法 1：使用 `isEmpty()` 方法

`TreeMap` 类的 `java.util.TreeMap.isEmpty()` 方法用于检查 `TreeMap` 是否为空。

### 语法

```java
TreeMap.isEmpty()
```

### 参数

该方法不取任何参数。

### 返回值

如果 `TreeMap` 为空，则该方法返回布尔值 `true`，否则返回 `false`。因此，如果 `TreeMap` 对象中至少有一个键值映射，它将返回 `false`，否则返回 `true`。

### 示例

```java
// Java Program to Check if the TreeMap is Empty
// using the isEmpty() method

// Importing TreeMap class of
// java.util package
import java.util.TreeMap;

public class GFG {

// Main driver method
    public static void main(String[] args)
    {

// Create an empty TreeMap
        TreeMap<Integer, String> tmap
            = new TreeMap<Integer, String>();

// Check TreeMap is empty or not
        boolean isEmpty = tmap.isEmpty();
        System.out.println("Is tmap empty :  " + isEmpty);

// Mapping string values to int keys
        tmap.put(1, "Geeks");
        tmap.put(2, "For");
        tmap.put(3, "skeeG");

// Displaying the TreeMap
        System.out.println("The Mappings are: " + tmap);

// Checking again TreeMap is empty or not
        isEmpty = tmap.isEmpty();

// Display boolean output again
        // to show isEmpty() method functionality
        System.out.println("Is tmap empty : " + isEmpty);

    }
}
```

### 输出

```java
Is tmap empty :  true
The Mappings are: {1=One, 2=Two}
Is tmap empty : false
```

## 方法 2：使用 `size()` 方法

`TreeMap` 类的 `java.util.TreeMap.size()` 方法通过大小与 0 的比较来检查 `TreeMap` 是否为空。如果 `TreeMap` 为空，则该方法返回 `true`，否则返回 `false`。

### 语法

```java
(TreeMap.size() == 0) ;
```

### 参数

该方法不取任何参数。

### 返回值

如果 `TreeMap` 为空，则该方法返回布尔值 `true`，否则返回 `false`。

### 示例

```java
// Java Program to Check if the TreeMap is Empty
// and illustrating the size() method

// Importing TreeMap class of
// java.util package
import java.util.TreeMap;

public class GFG {

// Main driver method
    public static void main(String[] args)
    {

// Create an empty TreeMap
        TreeMap<Integer, String> tmap
            = new TreeMap<Integer, String>();

// Check TreeMap is empty or not
        // Using size() method
        System.out.println("Is map empty : "
                           + (tmap.size() == 0));

// Mapping string values to int keys
        // Custom inputs mapping
        tmap.put(1, "One");
        tmap.put(2, "Two");

// Displaying the TreeMap
        System.out.println("The Mappings are: " + tmap);

// Display boolean output again
        // to show size() method functionality
        System.out.println("Is map empty : "
                           + (tmap.size() == 0));
    }
}
```

### 输出

```java
Is map empty : true
The Mappings are: {1=One, 2=Two}
Is map empty : false
```

**注意：** 相同的操作可以用任何类型的带有变化的映射和不同数据类型的组合来执行。