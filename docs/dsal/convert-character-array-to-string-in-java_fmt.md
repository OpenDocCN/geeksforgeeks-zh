# 在 Java 中将字符数组转换为字符串

> 原文：[https://www.geeksforgeeks.org/convert-character-array-to-string-in-java/](https://www.geeksforgeeks.org/convert-character-array-to-string-in-java/)

字符串被定义为字符数组。字符数组和字符串的区别在于字符串以特殊字符“\0”结尾。字符数组可以转换成字符串，反之亦然。在前一篇文章中，我们已经讨论了如何将[字符串转换为字符数组](https://www.geeksforgeeks.org/convert-a-string-to-character-array-in-java/)。在本文中，我们将讨论如何将字符数组转换为字符串。

**插图：**

```
Input  1 : char s[] = { 'g', 'e', 'e', 'k', 's', 'f', 'o', 'r', 'g', 'e', 'e', 'k', 's' } 
Output 1 : "geeksforgeeks" 
```

```
Input  2 : char s[] = { 'c', 'o', 'd', 'i', 'n', 'g' } 
Output 2 : "coding"
```

**方法：**

1.  使用 `Arrays` 类的 `copyOf()` 方法
2.  使用 `StringBuilder` 类
3.  使用 `String` 类的 `valueOf()` 方法
4.  使用 `String` 类的 `copyValueOf()` 方法
5.  在流中使用收集器

现在让我们详细讨论每种方法，并借助一个干净的 Java 程序来实现它们。

## 方法 1：使用 `Arrays` 类的 `copyOf()` 方法

给定的字符可以传递到 `String` 构造器中。默认情况下，字符数组内容是使用 `Arrays` 类中的 `Arrays.copyOf()` 方法复制的。

**例**

```java
// Java program to Convert Character Array to String
// Using copyOf() method of Arrays class

// Main class
class GFG {

    // Method 1
    // To convert a character
    // array to a string using the constructor
    public static String toString(char[] a)
    {
        // Creating object of String class
        String string = new String(a);

        return string;
    }

    // Main driver method
    public static void main(String args[])
    {
        // Character array
        char s[] = { 'g', 'e', 'e', 'k', 's', 'f', 'o',
                     'r', 'g', 'e', 'e', 'k', 's' };

        // Printing converted string from character array
        System.out.println(toString(s));
    }
}
```

**输出：**

```
geeksforgeeks
```

## 方法 2：使用 `StringBuilder` 类

将字符数组转换为字符串的另一种方法是使用 `StringBuilder` 类。由于 `StringBuilder` 是一个可变类，因此，其思想是遍历字符数组，并将每个字符追加到字符串的末尾。最后，字符串包含字符的字符串形式。

**例**

```java
// Java Program to Convert Character Array to String
// Using StringBuilder class

// importing required classes
import java.util.*;

// Main class
public class GFG {

    // Method
    // To convert a character array to a string
    // using the StringBuilder class
    public static String toString(char[] a)
    {
        // Creating object of String class
        StringBuilder sb = new StringBuilder();

        // Creating a string using append() method
        for (int i = 0; i < a.length; i++) {
            sb.append(a[i]);
        }

        return sb.toString();
    }

    // Method 2
    // Main driver method
    public static void main(String args[])
    {
        // Custom input as character array
        char s[] = { 'g', 'e', 'e', 'k',
                     's', 'f', 'o', 'r',
                     'g', 'e', 'e', 'k', 's' };

        // Printing the string
        // corresponding to character array
        System.out.println(toString(s));
    }
}
```

**Output**

```
geeksforgeeks
```