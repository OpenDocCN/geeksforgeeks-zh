# 使用递归反转句子的 Java 程序

> 原文：[`https://www.geeksforgeeks.org/java-program-to-reverse-a-sentence-using-recursion/`](https://www.geeksforgeeks.org/java-program-to-reverse-a-sentence-using-recursion/)

句子是由一些分隔符分隔的字符序列。这个字符序列从第 0 个索引开始，最后一个索引在 `len(string)-1`。通过反转字符串，我们从第 0 个索引开始交换字符，并从末尾开始放置它们。第一个字符变成最后一个，第二个变成第二个最后一个，以此类推。

**例：**

```java
Input : GeeksforGeeks
Output:    skeegrofskeeG

Input : Alice
Output: ecilA
```

**方法：**

1.  检查字符串是否为空，如果为空则返回 `null`。
2.  如果字符串为空，则返回一个空字符串。
3.  否则，返回字符串从索引 `1` 到字符串长度的 `substring` 部分与字符串第一个字符的连接。例如，返回 `substring(1) + str.charAt(0)`。也就是说，字符串 `"Mayur"` 的返回值将是 `"ayur" + "m"`。

下面是上述方法的实现：

```java
// Java Program to Reverse a Sentence Using Recursion
import java.io.*;

public class GFG {
    public static String reverse_sentence(String str)
    {
        // check if str is empty
        if (str.isEmpty())
            // return the string
            return str;
        else {
            // extract the character at 0th index, that is
            // the character at beginning
            char ch = str.charAt(0);

            // append character extracted at the end
            // and pass the remaining string to the function
            return reverse_sentence(str.substring(1)) + ch;
        }
    }

    public static void main(String[] args)
    {
        // specify the string to reverse
        String str = "Geeksforgeeks";

        // call the method to reverse sentence
        String rev_str = reverse_sentence(str);

        // print the reversed sentence
        System.out.println(
            "Sentence in reversed form is :  " + rev_str);

        // creating another string with numbers
        // and special characters
        String str2 = "Alice";

        String rev_str2 = reverse_sentence(str2);

        // print the reversed sentence
        System.out.println(
            "Sentence in reversed form is :  " + rev_str2);
    }
}
```

**输出**

**时间复杂度：** `O(N)`，其中 `N` 为字符串的长度。