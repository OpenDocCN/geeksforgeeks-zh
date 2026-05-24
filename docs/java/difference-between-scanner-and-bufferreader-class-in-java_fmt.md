# Java 中 Scanner 和 BufferedReader 类的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-scanner-and-bufferreader-class-in-java/](https://www.geeksforgeeks.org/difference-between-scanner-and-bufferreader-class-in-java/)

[`java.util.Scanner`](https://www.geeksforgeeks.org/scanner-class-in-java/) 类是一个简单的文本扫描器，可以解析原语类型和字符串。它在内部使用正则表达式来读取不同的类型。

[`BufferedReader`](https://www.geeksforgeeks.org/difference-between-scanner-and-bufferreader-class-in-java/) 类从字符输入流中读取文本，对字符进行缓冲，以便有效地读取字符序列。

以下是以上两者的区别。

## 在 `nextXXX()` 后使用 `nextLine()` 时的问题

使用 `Scanner` 时，请试猜以下代码的输出：

```java
// Code using Scanner Class
import java.util.Scanner;
class Differ
{
     public static void main(String args[])
     {
         Scanner scn = new Scanner(System.in);
         System.out.println("Enter an integer");
         int a = scn.nextInt();
         System.out.println("Enter a String");
         String b = scn.nextLine();
         System.out.printf("You have entered:- "
                 + a + " " + "and name as " + b);
     }
}
```

输入：

```java
Geek
```

输出：

```java
Enter an integer
Enter a String
You have entered:- 50 and name as
```

让我们使用 `BufferedReader` 类和相同的输入进行同样的尝试：

```java
// Code using Buffer Class
import java.io.*;
class Differ
{
    public static void main(String args[])
                  throws IOException
    {
        BufferedReader br = new BufferedReader(new
        InputStreamReader(System.in));
        System.out.println("Enter an integer");
        int a = Integer.parseInt(br.readLine());
        System.out.println("Enter a String");
        String b = br.readLine();
        System.out.printf("You have entered:- " + a +
                          " and name as " + b);
    }
}
```

输入：

```java
Geek
```

输出：

```java
Enter an integer
Enter a String
you have entered:- 50 and name as Geek
```

在 `Scanner` 类中，如果我们在七个 `nextXXX()` 方法中的任何一个之后调用 `nextLine()` 方法，那么 `nextLine()` 不会从控制台读取值，并且光标不会进入控制台，它将跳过该步骤。`nextXXX()` 方法是 `nextInt()`、`nextFloat()`、`nextByte()`、`nextShort()`、`nextDouble()`、`nextLong()`、`next()`。

在 `BufferedReader` 类中不存在这种类型的问题。这个问题只出现在 `Scanner` 类中，因为 `nextXXX()` 方法忽略换行符，而 `nextLine()` 只读取第一个换行符。如果我们在 `nextXXX()` 和 `nextLine()` 之间再调用一次 `nextLine()` 方法，那么就不会出现这个问题，因为 `nextLine()` 会消耗换行符。修正后的程序见[此](https://ide.geeksforgeeks.org/CErAhD)。

这个问题和 C/C++ 中 [`scanf()` 后跟 `get()`](https://www.geeksforgeeks.org/problem-with-scanf-when-there-is-fgetsgetsscanf-after-it/) 是一样的。

这个问题也可以用 `next()` 代替 `nextLine()` 进行字符串的输入来解决，如[这里](https://www.geeksforgeeks.org/problem-with-scanf-when-there-is-fgetsgetsscanf-after-it/)所示。

## 其他差异

*   `BufferedReader` 是同步的，而 `Scanner` 不是。如果我们使用多个线程，应该使用 `BufferedReader`。
*   `BufferedReader` 的缓冲内存比 `Scanner` 大得多。
*   `Scanner` 有一个小缓冲区（1KB 字符缓冲区），而不是 `BufferedReader` 的（8KB 字节缓冲区），但这已经足够了。
*   与 `Scanner` 相比，`BufferedReader` 速度稍快，因为 `Scanner` 对输入数据进行解析，`BufferedReader` 只是读取字符序列。

本文由**普拉纳夫·阿达什**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 `review-team@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息。