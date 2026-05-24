# 在字符串中打印偶数长度单词的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-print-even-length-words-in-a-string/](https://www.geeksforgeeks.org/java-program-to-print-even-length-words-in-a-string/)

给定一个字符串 `str`，编写一个 Java 程序，打印给定字符串中所有长度为偶数的单词。

**例：**

```java
Input: s = "This is a java language"
Output: This
        is
        java
        language

Input: s = "i am GFG"
Output: am
```

## 进场

*   获取字符串。
*   借助 `String` 类中的 `split()` 方法，将字符串拆分为单词。这是一个用于拆分句子的工具。这里传递 `""`（空格）作为参数。结果，字符串的单词被拆分到一个字符串数组中。

```java
    String[] words = str.split(" ");
```

*   借助 Java 中的 [foreach 循环](https://www.geeksforgeeks.org/for-each-loop-in-java/)，遍历返回的字符串数组中的每个单词。

```java
    for(String word : words)
    { }
```

*   使用 `string.length()` 函数计算每个单词的长度。

```java
    int lengthOfWord = word.length();
```

*   如果长度是偶数，则打印这个单词。

下面是上述方法的实现：

```java
// Java program to print
// even length words in a string

class GfG {
    public static void printWords(String s)
    {

// Splits Str into all possible tokens
        for (String word : s.split(" "))

// if length is even
            if (word.length() % 2 == 0)

// Print the word
                System.out.println(word);
    }

// Driver Code
    public static void main(String[] args)
    {

String s = "i am Geeks for Geeks and a Geek";
        printWords(s);
    }
}
```

**输出：**

```java
am
Geek
```