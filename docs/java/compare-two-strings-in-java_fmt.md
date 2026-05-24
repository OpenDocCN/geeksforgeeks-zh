# 在 Java 中比较两个字符串

> 原文：[https://www.geeksforgeeks.org/compare-two-strings-in-java/](https://www.geeksforgeeks.org/compare-two-strings-in-java/)

[字符串](https://www.geeksforgeeks.org/string-class-in-java/)是一个字符序列。在 Java 中，`String`的对象是不可变的，这意味着它们是常量，一旦创建就不能更改。

下面是用 Java 比较两个字符串的 5 种方法：

## 1. 使用自定义函数

定义一个函数来比较值，遵循以下条件：
1.  如果(`string1` > `string2`)，则返回一个**正值**。
2.  如果两个字符串在词典上相等（即 `string1` == `string2`），则返回 **0**。
3.  如果(`string1` < `string2`)，则返回一个**负值**。

该值计算为`(int)str1.charAt(i) - (int)str2.charAt(i)`。

### 示例

```java
Input 1: GeeksforGeeks
Input 2: Practice
Output: -9

Input 1: Geeks
Input 2: Geeks
Output: 0

Input 1: GeeksforGeeks
Input 2: Geeks
Output: 8
```

### 程序

```java
// Java program to Compare two strings
// lexicographically
public class GFG {

    // This method compares two strings
    // lexicographically without using
    // library functions
    public static int stringCompare(String str1, String str2)
    {
        int l1 = str1.length();
        int l2 = str2.length();
        int lmin = Math.min(l1, l2);

        for (int i = 0; i < lmin; i++) {
            int str1_ch = (int)str1.charAt(i);
            int str2_ch = (int)str2.charAt(i);

            if (str1_ch != str2_ch) {
                return str1_ch - str2_ch;
            }
        }

        // Edge case for strings like
        // String 1="Geeks" and String 2="Geeksforgeeks"
        if (l1 != l2) {
            return l1 - l2;
        }

        // If none of the above conditions is true,
        // it implies both the strings are equal
        else {
            return 0;
        }
    }

    // Driver function to test the above program
    public static void main(String args[])
    {
        String string1 = new String("Geeksforgeeks");
        String string2 = new String("Practice");
        String string3 = new String("Geeks");
        String string4 = new String("Geeks");

        // Comparing for String 1 < String 2
        System.out.println("Comparing " + string1 + " and " + string2
                           + " : " + stringCompare(string1, string2));

        // Comparing for String 3 = String 4
        System.out.println("Comparing " + string3 + " and " + string4
                           + " : " + stringCompare(string3, string4));

        // Comparing for String 1 > String 4
        System.out.println("Comparing " + string1 + " and " + string4
                           + " : " + stringCompare(string1, string4));
    }
}
```

### 输出

```java
Comparing Geeksforgeeks and Practice : -9
Comparing Geeks and Geeks : 0
Comparing Geeksforgeeks and Geeks : 8
```

## 2. 使用 `String.equals()`

在 Java 中，`String`的`equals()`方法根据字符串的数据/内容比较两个给定的字符串。如果两个字符串的所有内容都相同，则返回`true`。如果有任何字符不匹配，则返回`false`。

### 语法

```java
str1.equals(str2);
```

这里，`str1`和`str2`都是要比较的字符串。

### 示例

```java
Input 1: GeeksforGeeks
Input 2: Practice
Output: false

Input 1: Geeks
Input 2: Geeks
Output: true

Input 1: geeks
Input 2: Geeks
Output: false
```

### 程序

```java
// Java program to Compare two strings
// lexicographically
public class GFG {
    public static void main(String args[])
    {
        String string1 = new String("Geeksforgeeks");
        String string2 = new String("Practice");
        String string3 = new String("Geeks");
        String string4 = new String("Geeks");
        String string5 = new String("geeks");

        // Comparing for String 1 != String 2
        System.out.println("Comparing " + string1 + " and " + string2
                           + " : " + string1.equals(string2));

        // Comparing for String 3 = String 4
        System.out.println("Comparing " + string3 + " and " + string4
                           + " : " + string3.equals(string4));

        // Comparing for String 4 != String 5
        System.out.println("Comparing " + string4 + " and " + string5
                           + " : " + string4.equals(string5));

        // Comparing for String 1 != String 4
        System.out.println("Comparing " + string1 + " and " + string4
                           + " : " + string1.equals(string4));
    }
}
```

### 输出

```java
Comparing Geeksforgeeks and Practice : false
Comparing Geeks and Geeks : true
Comparing Geeks and geeks : false
Comparing Geeksforgeeks and Geeks : false
```

## 3. 使用 `String.equalsIgnoreCase()`

[`String.equalsIgnoreCase()`](https://www.geeksforgeeks.org/equalsignorecase-in-java/)方法比较两个字符串，而不考虑字符串的大小写（小写或大写）。如果参数不为`null`且两个字符串的内容相同（忽略大小写），则此方法返回`true`，否则返回`false`。

### 语法

```java
str2.equalsIgnoreCase(str1);
```

这里，`str1`和`str2`都是要比较的字符串。

### 示例

```java
Input 1: GeeksforGeeks
Input 2: Practice
Output: false

Input 1: Geeks
Input 2: Geeks
Output: true

Input 1: geeks
Input 2: Geeks
Output: true
```

### 程序

```java
// Java program to Compare two strings
// lexicographically
public class GFG {
    public static void main(String args[])
    {
        String string1 = new String("Geeksforgeeks");
        String string2 = new String("Practice");
        String string3 = new String("Geeks");
        String string4 = new String("Geeks");
        String string5 = new String("geeks");

        // Comparing for String 1 != String 2
        System.out.println("Comparing " + string1 + " and " + string2
                           + " : " + string1.equalsIgnoreCase(string2));

        // Comparing for String 3 = String 4
        System.out.println("Comparing " + string3 + " and " + string4
                           + " : " + string3.equalsIgnoreCase(string4));

        // Comparing for String 4 = String 5
        System.out.println("Comparing " + string4 + " and " + string5
                           + " : " + string4.equalsIgnoreCase(string5));

        // Comparing for String 1 != String 4
        System.out.println("Comparing " + string1 + " and " + string4
                           + " : " + string1.equalsIgnoreCase(string4));
    }
}
```

### 输出

```java
Comparing Geeksforgeeks and Practice : false
Comparing Geeks and Geeks : true
Comparing Geeks and geeks : true
Comparing Geeksforgeeks and Geeks : false
```

## 4. 使用 `Objects.equals()`

[`Object.equals(Object a, Object b)`](https://www.geeksforgeeks.org/java-util-objects-class-java/)方法在参数彼此相等时返回`true`，否则返回`false`。因此，如果两个参数都为`null`，则返回`true`；如果只有一个参数为`null`，则返回`false`。否则，使用第一个参数的`equals()`方法确定相等性。

### 语法

```java
public static boolean equals(Object a, Object b)
```

这里`a`和`b`都是要比较的字符串对象。

### 示例

```java
Input 1: GeeksforGeeks
Input 2: Practice
Output: false

Input 1: Geeks
Input 2: Geeks
Output: true

Input 1: null
Input 2: null
Output: true
```

### 程序

```java
// Java program to Compare two strings
// lexicographically
import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        String string1 = new String("Geeksforgeeks");
        String string2 = new String("Geeks");
        String string3 = new String("Geeks");
        String string4 = null;
        String string5 = null;
```

## 5. Using String.compareTo()

**语法:**

```java
int str1.compareTo(String str2)
```

**工作:**
它比较并返回如下值:

1.  如果(`string1` > `string2`)，则返回一个**正值**。
2.  如果两个字符串在词典上相等 (即 `string1` == `string2`)，则返回 **0**。
3.  如果(`string1` < `string2`)，则返回一个**负值**。

**示例:**

```java
Input 1: GeeksforGeeks
Input 2: Practice
Output: -9

Input 1: Geeks
Input 2: Geeks
Output: 0

Input 1: GeeksforGeeks
Input 2: Geeks
Output: 8
```

**程序:**

```java
// Java program to Compare two strings
// lexicographically

import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        String string1 = new String("Geeksforgeeks");
        String string2 = new String("Practice");
        String string3 = new String("Geeks");
        String string4 = new String("Geeks");

        // Comparing for String 1 < String 2
        System.out.println("Comparing " + string1 + " and " + string2
                           + " : " + string1.compareTo(string2));

        // Comparing for String 3 = String 4
        System.out.println("Comparing " + string3 + " and " + string4
                           + " : " + string3.compareTo(string4));

        // Comparing for String 1 > String 4
        System.out.println("Comparing " + string1 + " and " + string4
                           + " : " + string1.compareTo(string4));
    }
}
```

**Output:**

```java
Comparing Geeksforgeeks and Practice : -9
Comparing Geeks and Geeks : 0
Comparing Geeksforgeeks and Geeks : 8
```

## 为什么不用==来比较字符串？

一般来说，Java 中的 `equals()` 和 `==` 运算符都用于比较对象以检查相等性，但以下是两者之间的一些区别:

*   `equals()` 方法和 `==` 运算符之间的主要区别是一个是方法，另一个是运算符。
*   可以使用 `==` 运算符进行引用比较 **(地址比较)**，而使用 `.equals()` 方法进行 **内容比较**。

简单来说，`==` 检查两个对象是否指向同一个内存位置，反之 `equals()` 计算对象中值的比较。

**示例:**

```java
// Java program to understand
// why to avoid == operator

public class Test {
    public static void main(String[] args)
    {
        String s1 = new String("HELLO");
        String s2 = new String("HELLO");

        System.out.println(s1 == s2);

        System.out.println(s1.equals(s2));
    }
}
```

**Output:**

```java
false
true
```

**说明:** 这里正在创建两个字符串对象，即 `s1` 和 `s2`。

*   `s1` 和 `s2` 指向不同的对象。
*   当使用 `==` 运算符进行 `s1` 和 `s2` 比较时，结果为假，因为两者在内存中的地址不同。
*   使用 `equals`，结果为真，因为它只比较 `s1` 和 `s2` 中给出的值。