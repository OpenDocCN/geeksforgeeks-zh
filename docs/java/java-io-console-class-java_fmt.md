# Java 中的 Java.io.Console 类

> 原文：[https://www.geeksforgeeks.org/java-io-console-class-java/](https://www.geeksforgeeks.org/java-io-console-class-java/)

`Java.io.Console` 类提供了访问与当前 Java 虚拟机关联的基于字符的控制台设备（如果有）的方法。`Console` 类是由 JDK 6 添加到 `java.io` 中的。

## 要点

*   它用于从控制台读写（如果有）。
*   控制台主要是一个便利类，因为它的大部分功能都可以通过 `System.in` 和 `System.out` 获得。但是，它的使用可以简化某些类型的控制台交互，尤其是在从控制台读取字符串时。
*   `Console` 未提供构造方法。相反，`Console` 对象是通过调用 `System.console()` 获得的，如下所示：
    ```java
    static Console console()
    ```
    如果控制台可用，则返回对它的引用。否则，返回 `null`。控制台并非在所有情况下都可用。因此，如果返回空值，就不可能有控制台输入/输出。
*   它提供了读取文本和密码的方法。如果您使用 `Console` 类读取密码，它将不会显示给用户。`java.io.Console` 类与系统控制台内部相连。

## 重要方法

### `writer`
检索与此控制台关联的唯一 `PrintWriter` 对象。
**语法：**
```java
public PrintWriter writer()
```
**返回：** 与此控制台关联的 `PrintWriter`。

### `reader`
检索与此控制台关联的唯一 `Reader` 对象。
**语法：**
```java
public Reader reader()
```
**返回：** 与此控制台关联的 `Reader`。

### `format`
使用指定的格式字符串和参数将格式化字符串写入控制台的输出流。
**语法：**
```java
public Console format(String fmt, Object... args)
```
**参数：**
*   `fmt` - 如格式字符串语法所述的格式字符串。
*   `args` - 由格式字符串中的格式说明符引用的参数。如果参数多于格式说明符，则忽略额外的参数。
**返回：** 此 `Console`。
**抛出：** `IllegalFormatException`

### `printf`
使用指定的格式字符串和参数将格式化字符串写入控制台输出流的便捷方法。
**语法：**
```java
public Console printf(String format, Object... args)
```
**参数：**
*   `format` - 如格式字符串语法所述的格式字符串。
*   `args` - 由格式字符串中的格式说明符引用的参数。如果参数多于格式说明符，则忽略额外的参数。
**返回：** 此 `Console`。
**抛出：** `IllegalFormatException`

### `readLine`
提供格式化提示，然后从控制台读取单行文本。
**语法：**
```java
public String readLine(String fmt, Object... args)
```
**参数：**
*   `fmt` - 如格式字符串语法所述的格式字符串。
*   `args` - 由格式字符串中的格式说明符引用的参数。如果参数多于格式说明符，则忽略额外的参数。
**返回：** 一个包含从控制台读取的行的字符串，不包括任何行终止符，如果已到达流末尾，则返回 `null`。
**抛出：** `IllegalFormatException`, `IOError`（如果发生 I/O 错误）。

### `readLine`
从控制台读取单行文本。
**语法：**
```java
public String readLine()
```
**返回：** 一个包含从控制台读取的行的字符串，不包括任何行终止符，如果已到达流末尾，则返回 `null`。
**抛出：** `IOError`

### `readPassword`
提供格式化提示，然后在禁用回显的情况下从控制台读取密码或密码短语。
**语法：**
```java
public char[] readPassword(String fmt, Object... args)
```
**参数：**
*   `fmt` - 如格式字符串语法所述的提示文本格式字符串。
*   `args` - 由格式字符串中的格式说明符引用的参数。
**返回：** 一个包含从控制台读取的密码或密码短语的字符数组，不包括任何行终止符，如果已到达流末尾，则返回 `null`。
**抛出：** `IllegalFormatException`, `IOError`

### `readPassword`
从禁用回显的控制台读取密码或密码短语。
**语法：**
```java
public char[] readPassword()
```
**返回：** 一个包含从控制台读取的密码或密码短语的字符数组，不包括任何行终止符，如果已到达流末尾，则返回 `null`。
**抛出：** `IOError`

### `flush`
刷新控制台并强制立即写入任何缓冲的输出。
**语法：**
```java
public void flush()
```
**指定者：** 接口 `Flushable` 中的 `flush`。

## 程序
```java
// Java Program to demonstrate Console Methods
import java.io.*;

class ConsoleDemo {
    public static void main(String args[]) {
        String str;

        // Obtaining a reference to the console.
        Console con = System.console();

        // Checking If there is no console available, then exit.
        if (con == null) {
            System.out.print("No console available");
            return;
        }

        // Read a string and then display it.
        str = con.readLine("Enter your name: ");
        con.printf("Here is your name: %s\n", str);

        // to read password and then display it
        System.out.println("Enter the password: ");
        char[] ch = con.readPassword();

        // converting char array into string
        String pass = String.valueOf(ch);
        System.out.println("Password is: " + pass);
    }
}
```

## 输出
```
Enter your name: Nishant Sharma
Here is your name: Nishant Sharma
Enter the password: 
Password is: dada
```

注意：`System.console()` 在联机 IDE 中返回空值。

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。