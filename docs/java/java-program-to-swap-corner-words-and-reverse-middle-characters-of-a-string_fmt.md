# 交换角字和反转字符串中间字符的 Java 程序

> 原文: [https://www.geeksforgeeks.org/java-program-to-swap-corner-words-and-reverse-middle-characters-of-a-string/](https://www.geeksforgeeks.org/java-program-to-swap-corner-words-and-reverse-middle-characters-of-a-string/)

给定一个包含 n 个单词的字符串。任务是交换字符串的角单词并反转字符串的所有中间字符。

```
Input:  "Hello this is the GFG user"
Output: "user GFG eth si siht Hello"
Input:  "Hello Bye"
Output: "Bye Hello"
```

## 方法

1.  使用 ASCII 值的概念
2.  使用 `split()` 方法

## 方法 1: 使用 ASCII 值的概念

我们使用 ASCII 值来处理单词之间的空格位置。空格的 ASCII 值是 32。

1.  创建两个字符串变量和两个指针，让名称成为 `index` 和 `index1`。
2.  使用 `index` 地址变量迭代第一个循环，直到第一个空格，并将所有字符存储在名为 `first` 的字符串变量中。
3.  使用 `index1` 地址变量从相反的顺序迭代另一个循环，直到第一个空格，并将另一个字符串变量名中的所有字符存储为 `last`。
4.  现在，我们有了地址变量 `index1` 和 `index`，它们都指向给定字符串中间字符的下一个开始和结束位置。
5.  使用这两个指针将所有字符以相反的顺序存储在名为 `middle` 的第三个字符串变量中。
6.  打印 `last` 字符串，然后是 `middle` 的字符串，然后是 `first` 字符串。

### 示例

#### Java

```java
// Java Program to Swap Corner Words and Reverse Middle
// Characters

// Importing utility classes
import java.util.*;
// Importing input output classes
import java.io.*;

// Main class
public class GFG {

    // Method 1
    // To swap corners words
    static void swap(String m, int length)
    {

        // Declaring string variables to
        // store the first and last characters
        String first = "";
        String last = "";

        // Creating first address variable
        // Initially initializing with zero
        int index = 0;

        for (index = 0; index < length; ++index) {

            // Checking the space
            if (m.charAt(index) == 32) {
                break;
            }

            // Storing the last word in the last variable
            last += m.charAt(index);
        }

        // Now creating second address variable
        // Initially initializing with zero
        int index1 = 0;

        for (index1 = length - 1; index1 >= 0; --index1) {
            if (m.charAt(index1) == 32) {
                break;
            }

            // Storing the First word of the given string
            first = m.charAt(index1) + first;
        }

        String middle = "";
        for (int i = index1 - 1; i > index; --i) {
            if (m.charAt(i) == 32) {
                middle += " ";
            }
            else {

                // Storing all the middle words
                middle += m.charAt(i);
            }
        }

        // Print and display all the string variables
        System.out.print(first + " " + middle + " " + last);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Given custom input string
        String m = "Hello this is the GFG";

        // Calculating string length using length() method
        // and storing it in a variable
        int length = m.length();

        // Calling the method 1 to swap the words
        // for our custom input string
        swap(m, length);
    }
}
```

### 输出

```java
GFG eht si siht Hello
```

## 方法 2: 使用 `split()` 方法

`String split()` 方法在给定正则表达式的匹配项周围断开给定的字符串。

### 插图

```
Input        : 016-78967
Processing    : Regular Expression
Output       : {"016", "78967"}
```

### 过程

*   使用 `split()` 方法将所有单词存储在数组中。
*   交换数组的第一个和最后一个元素。
*   从第二个位置迭代到最后第二个位置。
*   将所有字符以相反的顺序存储在名为 `mid` 的中间变量中。
*   打印数组的第一个元素，然后是 `mid` 变量，然后是数组的最后一个元素。

### 示例

#### Java

```java
// Java Program to Swap Corner Words and Reverse Middle
// Characters

// Importing utility classes
// Importing input output classes
import java.io.*;
import java.util.*;

// Main class
public class GFG {

    // Method 1
    // To swap the words in a string
    static void swap(String m, int length)
    {
        // Storing the words in the array
        String msg[] = m.split(" ");

        // Now swap the position of the first and the last
        // character in the string array
        String temp = msg[0];
        msg[0] = msg[msg.length - 1];
        msg[msg.length - 1] = temp;

        // Declaring and initializing string for
        // middle string empty middle string
        String mid = "";

        for (int i = msg.length - 2; i >= 1; --i) {
            String temp_s = msg[i];

            // Now storing the middle words in reverse order
            for (int j = temp_s.length() - 1; j >= 0; --j) {
                mid += temp_s.charAt(j);
            }
            mid += " ";
        }

        // Lastly print the swapped and reversed words
        System.out.print(msg[0] + " " + mid + " "
                         + msg[msg.length - 1]);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input string
        String m = "Hello this is the GFG";

        // Calculating length using length() method and
        // storing it
        int length = m.length();

        // Calling the method 1 over custom input string to
        // get swapped corner words with reverse middle
        // characters
        swap(m, length);
    }
}
```

### 输出

```java
GFG eht si siht  Hello
```