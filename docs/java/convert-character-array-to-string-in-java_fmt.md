# 在 Java 中将字符数组转换为字符串

> 原文：[https://www.geeksforgeeks.org/convert-character-array-to-string-in-java/](https://www.geeksforgeeks.org/convert-character-array-to-string-in-java/)

字符串被定义为字符数组。字符数组和字符串的区别在于字符串以特殊字符“\0”结尾。字符数组可以转换成字符串，反之亦然。在前一篇文章中，我们已经讨论了如何将[字符串转换为字符数组](https://www.geeksforgeeks.org/convert-a-string-to-character-array-in-java/)。在本文中，我们将讨论如何将字符数组转换为字符串。

**插图：**

```java
Input  1 : char s[] = { 'g', 'e', 'e', 'k', 's', 'f', 'o', 'r', 'g', 'e', 'e', 'k', 's' } 
Output 1 : "geeksforgeeks" 
```

```java
Input  2 : char s[] = { 'c', 'o', 'd', 'i', 'n', 'g' } 
Output 2 : "coding"
```

**方法：**

1.  使用 `Arrays` 类的 `copyOf()` 方法
2.  使用 `StringBuilder` 类
3.  使用 `String` 类的 `valueOf()` 方法
4.  使用 `String` 类的 `copyValueOf()` 方法
5.  在流中使用收集器

现在让我们详细讨论每种方法，并借助一个干净的 java 程序来实现它们。

## 方法 1：使用 `Arrays` 类的 `copyOf()` 方法

给定的字符可以传递到 `String` 构造器中。默认情况下，字符数组内容是使用 `Arrays` 类中的 `Arrays.copyOf()` 方法复制的。

**例**

```java
// Java program to Convert Character Array to String
// Using copyOf() method ofArrays class

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

```java
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

```java
geeksforgeeks
```

## 方法 3：使用 `String` 类的 `valueOf()` 方法

将字符数组转换为字符串的另一种方法是使用 `String` 类中的 `valueOf()` 方法。此方法固有地将字符数组转换为显示数组中字符的整个值的格式。此方法通常将 `int`、`float`、`double`、`char`、`boolean` 甚至 `object` 转换为字符串。在这里，我们将通过将我们的字符数组转换为字符串来实现这个目标。

**例**

```java
// Java program to Convert Character Array to String
// Using valueOf() method of String class

// Main class
class GFG {

    // Method 1
  // To convert a character array to string
  // using the valueOf() method
    public static String toString(char[] a)
    {
        // Creating an object of String class
        String string = String.valueOf(a);

        return string;
    }

    // Method 2
    // Main driver method
    public static void main(String args[])
    {

        // Custom input character array
        char s[] = { 'g', 'e', 'e', 'k',
                     's', 'f', 'o', 'r',
                     'g', 'e', 'e', 'k', 's' };

        // Print the corresponding string to
        // character array 
        System.out.println(toString(s));
    }
}
```

**Output**

```java
geeksforgeeks
```

## 方法 4：使用 `String` 类的 `copyValueOf()` 方法

字符数组中的内容会在不影响要返回的字符串的情况下被复制和修改，因此该方法也使我们能够将字符数组转换为字符串，从下面提供的示例中可以更好地理解字符串。

**例**

```java
// Java program to Convert Character Array to String
// Using copyValueOf() method of String class

// Importing String class
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args) {

        // Customly declaring an input character array
        char[] arr = { 'g', 'e', 'e', 'k',
                       's', 'f', 'o', 'r',
                       'g', 'e', 'e', 'k', 's'
                     };

        // Using copyValueOf() over string and
        // storing it in a string
        String str = String.copyValueOf(arr);

        // Printing the converted string corresponding
        // character array
        System.out.print(str);
    }
}
```

**Output**

```java
geeksforgeeks
```

## 方法 5：在流中使用收集器

随着 java8 中流的引入，我们直接使用流中的 `joining()` 方法并返回单个字符串并打印它。

**例**

```java
// Java Program to Convert a Character array to String
// Using Collectors in Streams in Java8

// Importing Collectos and Stream classes
// from java.util.stream package
import java.util.stream.Collectors;
import java.util.stream.Stream;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Custom input character array
        char[] charr = { 'g', 'e', 'e', 'k', 's', 'f', 'o',
                         'r', 'g', 'e', 'e', 'k', 's' };

        // Using collectors to collect array elements and
        // later using joining method to return a single
        // string
        String str = Stream.of(charr)
                           .map(arr -> new String(arr))
                           .collect(Collectors.joining());

        // Printing the stream received from Collectors
        System.out.println(str);
    }
}
```

**Output**

```java
geeksforgeeks
```