# 如何检查 Java 中的 LinkedHashMap 大小？

> 原文: [https://www.geeksforgeeks.org/how-to-check-the-linkedhashmap-size-in-java/](https://www.geeksforgeeks.org/how-to-check-the-linkedhashmap-size-in-java/)

[`LinkedHashMap`](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 的大小可以通过多种方式获得，比如使用内置函数和迭代 [`LinkedHashMap`](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)。

**示例:**

```java
Input : List : [1 : "John", 2 : "Tom", 3 : "Tim"]
Output: 3

Input : List : [1 : "John", 2 : "Tom"]
Output: 2
```

## 方法 1: 使用迭代

1.  创建一个整数数据类型的大小变量 `size`，并用 0 初始化它。
2.  开始遍历 [`LinkedHashMap`](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)，并在每次迭代时增加 `size` 变量。
3.  迭代完成后，打印 `size` 变量。

下面是上述方法的实现:

```java
// Java Program to find the size of LinkedHashMap
import java.util.*;
public class LinkedHashMapSizeExample {

    public static void main(String[] args)
    {
        // LinkedHashMap Initialization
        LinkedHashMap<Integer, String> lhMapColors
            = new LinkedHashMap<Integer, String>();

        lhMapColors.put(1, "red");
        lhMapColors.put(2, "white");
        lhMapColors.put(3, "blue");

        // Create of size variable and initialize with 0
        int size = 0;
        for (Map.Entry mapElement :
             lhMapColors.entrySet()) {
            size++;
        }
        System.out.println("Size of LinkedHashMap is "
                           + size);
    }
}
```

**Output**

```java
Size of LinkedHashMap is 3
```

## 方法 2: 使用 `size()` 方法

**语法:**

```java
List.size()
```

**返回类型:**

```java
Integer
```

1.  创建整数数据类型的 `size` 变量，并使用 `size()` 方法对其进行初始化。
2.  打印 `size` 变量。

下面是上述方法的实现:

```java
// Java Program to find the size of LinkedHashMap
import java.util.LinkedHashMap;
public class LinkedHashMapSizeExample {

    public static void main(String[] args)
    {
        // Initialize LinkedHashMap
        LinkedHashMap<Integer, String> lhMapColors
            = new LinkedHashMap<Integer, String>();

        // Add elements
        lhMapColors.put(1, "red");
        lhMapColors.put(2, "white");
        lhMapColors.put(3, "blue");

        // Create size variable and initialize
        // it with size() method
        int size = lhMapColors.size();
        System.out.println("Size of LinkedHashMap is "
                           + size);
    }
}
```

**Output**

```java
Size of LinkedHashMap is 3
```