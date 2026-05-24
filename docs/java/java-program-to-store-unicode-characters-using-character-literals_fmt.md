# 使用字符文字存储 Unicode 字符的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-store-unicode-characters-using-character-literals/](https://www.geeksforgeeks.org/java-program-to-store-unicode-characters-using-character-literals/)

Unicode 字符是通用字符编码标准。它代表了不同的字符在不同的文档中的表现方式，如文本文件、网页等。Unicode 支持 4 个字节的字符。UTF-8 已经成为标准字符编码，它支持每个字符 4 个字节。还有其他不同的 Unicode 编码，如 UTF-16、UTF-8。Java 中的字符文字是 Java 中的常量字符。它们用单引号括起来，例如 `'A'`、`'1'`、`'~'`、`'$'`、`'/'`、`'π'`。可以存储字符文字的数据类型是 `char`。通过使用下面给出的三种方法：

## 方法 1：为字符数据类型分配 Unicode

**示例：**

```java
Input : a = '$';
Output: $

Input : a = '~' 
Output: ~
```

**步骤：**

1.  创建一个 `char` 变量。
2.  使用单引号将 Unicode 字符存储在变量中。
3.  打印变量。

### Java 实现

```java
// Assigning Unicode to the char data types
import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        char c1 = 'a';
        System.out.println(c1);
        char c2 = 'A';
        System.out.println(c2);
        char c3 = '1';
        System.out.println(c3);
        char c4 = '~';
        System.out.println(c4);
        char c5 = '$';
        System.out.println(c5);
        char c6 = '/';
        System.out.println(c6);
        char c7 = 'π';
        System.out.println(c7);
    }
}
```

**输出**

```java
a
A
1
~
$
/
π
```

## 方法 2：为字符数据类型分配 Unicode 值

**示例：**

```java
Input : a = '\u0061'
Output: a

Input : a = '\u002F' 
Output: /
```

**步骤：**

1.  创建一个 `char` 变量。
2.  使用单引号将 Unicode 值存储在变量中。
3.  打印变量。

### Java 实现

```java
// Assigning Unicode values to char data types
import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        char c1 = '\u0061';
        System.out.println(c1);
        char c2 = '\u0041';
        System.out.println(c2);
        char c3 = '\u0031';
        System.out.println(c3);
        char c4 = '\u007E';
        System.out.println(c4);
        char c5 = '\u0024';
        System.out.println(c5);
        char c6 = '\u002F';
        System.out.println(c6);
        char c7 = '\u03C0';
        System.out.println(c7);
    }
}
```

**输出**

```java
a
A
1
~
$
/
π
```

## 方法 3：为字符数据类型分配 ASCII 值

**示例：**

```java
Input : a = 97
Output: a

Input : a = 49 
Output: 1
```

**步骤：**

1.  创建一个 `char` 变量。
2.  使用单引号将 ASCII 值存储在变量中。
3.  打印变量。

### Java 实现

```java
// Assigning ASCII values to char data types
import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        char c1 = 97;
        System.out.println(c1);
        char c2 = 65;
        System.out.println(c2);
        char c3 = 49;
        System.out.println(c3);
        char c4 = 126;
        System.out.println(c4);
        char c5 = 36;
        System.out.println(c5);
        char c6 = 47;
        System.out.println(c6);
    }
}
```

**输出**

```java
a
A
1
~
$
/
```