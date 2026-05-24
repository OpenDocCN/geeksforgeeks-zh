# 如何在 Java 中找到字符串的第一个和最后一个字符

> 原文：[https://www.geeksforgeeks.org/how-to-find-the-first-and-last-character-of-a-string-in-java/](https://www.geeksforgeeks.org/how-to-find-the-first-and-last-character-of-a-string-in-java/)

给定一个字符串 `str`，任务是打印字符串的第一个和最后一个字符。

**示例：**

> **输入：** `str = "GeeksForGeeks"`
> 
> **输出：**
> 
> 第一：G
> 
> 最后：s
> 
> **说明：** 给定字符串的第一个字符是‘G’，给定字符串的最后一个字符是‘s’。
> 
> **输入：** `str = "Java"`
> 
> **输出：**
> 
> 第一：J
> 
> 最后：a
> 
> **说明：** 给定字符串的第一个字符是‘J’，给定字符串的最后一个字符是‘a’。

## 方法 1：使用 `String.charAt()` 方法

*   想法是使用 `String` 类的 `charAt()` 方法来查找字符串中的第一个和最后一个字符。
*   `charAt()` 方法接受一个参数作为要返回的字符的索引。
*   字符串中的第一个字符出现在索引 `0` 处，字符串中的最后一个字符出现在字符串长度减 1 的索引处。
*   现在，打印字符串的第一个和最后一个字符。

下面是上述方法的实现：

```java
// Java program to find first
// and last character of a string

class GFG {

    // Function to print first and last
    // character of a string
    public static void
    firstAndLastCharacter(String str)
    {

        // Finding string length
        int n = str.length();

        // First character of a string
        char first = str.charAt(0);

        // Last character of a string
        char last = str.charAt(n - 1);

        // Printing first and last
        // character of a string
        System.out.println("First: " + first);
        System.out.println("Last: " + last);
    }

    // Driver Code
    public static void main(String args[])
    {
        // Given string str
        String str = "GeeksForGeeks";

        // Function Call
        firstAndLastCharacter(str);
    }
}
```

**Output：**

```
First: G
Last: s
```

## 方法二：使用 `toCharArray()` 方法

*   其思想是首先使用 `String` 类的 `toCharArray()` 方法将给定的字符串转换成字符数组，然后找到字符串的第一个和最后一个字符并打印出来。

下面是上述方法的实现：

```java
// Java program to find first
// and last character of a string

class GFG {

    // Function to print first and last
    // character of a string
    public static void
    firstAndLastCharacter(String str)
    {
        // Converting a string into
        // a character array
        char[] charArray = str.toCharArray();

        // Finding the length of
        // character array
        int n = charArray.length;

        // First character of a string
        char first = charArray[0];

        // Last character of a string
        char last = charArray[n - 1];

        // Printing first and last
        // character of a string
        System.out.println("First: " + first);
        System.out.println("Last: " + last);
    }

    // Driver Code
    public static void main(String args[])
    {
        // Given string str
        String str = "GeeksForGeeks";

        // Function Call
        firstAndLastCharacter(str);
    }
}
```

**Output：**

```
First: G
Last: s
```