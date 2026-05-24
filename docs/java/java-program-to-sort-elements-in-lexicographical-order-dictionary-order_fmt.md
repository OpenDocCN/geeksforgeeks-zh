# 按照字典顺序对元素进行排序的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-sort-elements-in-lexicographical-order-dictionary-order/](https://www.geeksforgeeks.org/java-program-to-sort-elements-in-lexicographical-order-dictionary-order/)

使用两种方法按**字典顺序**排序：

1.  对字符串数组排序：使用任意排序技术对数组元素进行排序。
2.  使用 Java util 包中 `Arrays` 类的 `sort()` 函数。

**例：**

```java
Input : Harit Girish Gritav Lovenish Nikhil Harman 
Output: Girish Gritav Harit Harman Lovenish Nikhil

Input : Bob Alice
Output: Alice Bob
```

## 方法 1：简单排序技术

在这种方法中，使用 `String` 类的 `compareToIgnoreCase()` 方法比较两个字符串。

### 使用的功能

```java
int compareToIgnoreCase(String);
```

### 返回值

1.  如果参数是与该字符串字典顺序相等的字符串，则返回 0。
2.  如果参数是字典顺序大于该字符串的字符串，则返回小于 0 的值。
3.  如果参数是字典顺序小于该字符串的字符串，则返回大于 0 的值。

一个使用排序技术的 Java 程序：

### Java

```java
// Java Program to Sort Elements in
// Lexicographical Order (Dictionary Order)
import java.io.*;

class GFG {

    // this method sort the string array lexicographically.
    public static void sortLexicographically(String strArr[])
    {
        for (int i = 0; i < strArr.length; i++) {
            for (int j = i + 1; j < strArr.length; j++) {
                if (strArr[i].compareToIgnoreCase(strArr[j])
                    > 0) {
                    String temp = strArr[i];
                    strArr[i] = strArr[j];
                    strArr[j] = temp;
                }
            }
        }
    }

    // this function prints the array passed as argument
    public static void printArray(String strArr[])
    {
        for (String string : strArr)
            System.out.print(string + " ");
        System.out.println();
    }

    public static void main(String[] args)
    {
        // Initializing String array.
        String stringArray[]
            = { "Harit",    "Girish", "Gritav",
                "Lovenish", "Nikhil", "Harman" };

        // sorting String array lexicographically.
        sortLexicographically(stringArray);

        printArray(stringArray);
    }
}
```

### 输出

```java
Girish Gritav Harit Harman Lovenish Nikhil
```

**时间复杂度：** O(n<sup>2</sup>)，其中 n 是数组的大小。

## 方法 2：使用 `Arrays.sort()`

在这种方法中，使用了 `java.utils.Arrays` 类中的 `sort()` 方法。

### 使用的功能

```java
Arrays.sort(stringArray, String.CASE_INSENSITIVE_ORDER);

// First Parameter : Name of Array
// Second Parameter: Special command to ignore case while sorting.
```

一个使用 `Arrays.sort()` 方法的 Java 程序：

### Java

```java
// Java Program to Sort Elements in
// Lexicographical Order (Dictionary Order)
import java.io.*;
import java.util.Arrays;

class GFG {
    // this function prints the array passed as argument
    public static void printArray(String strArr[])
    {
        for (String string : strArr)
            System.out.print(string + " ");
        System.out.println();
    }
    public static void main(String[] args)
    {
        // Initializing String array.
        String stringArray[]
            = { "Harit",    "Girish", "Gritav",
                "Lovenish", "Nikhil", "Harman" };

        // sorting String array in Lexicographical Order.
        // Ignoring the case of string.
        Arrays.sort(stringArray,
                    String.CASE_INSENSITIVE_ORDER);

        // printing String array after sorting.
        printArray(stringArray);
    }
}
```

### 输出

```java
Girish Gritav Harit Harman Lovenish Nikhil
```

**时间复杂度：** O(n log n)