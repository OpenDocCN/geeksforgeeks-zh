# 字符集解码器检测到 Java 中的 Charset()方法，示例

> 原文:[https://www . geesforgeks . org/charsetdecoder-detected charset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetdecoder-detectedcharset-method-in-java-with-examples/)

`detectedCharset()` 方法是 `java.nio.charset.CharsetDecoder` 类的一个内置方法，用于获取此解码器已检测到的字符集。该方法的默认实现总是抛出 `UnsupportedOperationException`。一旦输入字符集确定，自动检测解码器应将其置位，使其返回真。

## 语法

```java
public Charset detectedCharset()
```

## 参数

该功能不接受任何参数。

## 返回值

该函数返回该解码器检测到的字符集。

## 异常

如果该解码器没有实现自动检测字符集，它将抛出 `UnsupportedOperationException`，如果没有读取足够的字节来确定字符集，它将抛出 `IllegalStateException`。

下面是上述功能的实现:

## 程序 1

```java
// Java program to demonstrate
// the above function

import java.nio.charset.*;
import java.util.Iterator;
import java.util.Map;

public class GFG {

public static void main(String[] args)
    {

// Gets the charset
        Charset charset = Charset.forName("ISO-2022-CN");

// Get the CharsetDecoder
        CharsetDecoder decoder = charset.newDecoder();

// Prints the CharsetDecoder
        System.out.println("CharsetDecoder: " + decoder);

try {
            System.out.println("detected Charset: "
                               + decoder.detectedCharset());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

## 输出

```java
CharsetDecoder: sun.nio.cs.ext.ISO2022_CN$Decoder@232204a1
java.lang.UnsupportedOperationException
```

## 程序二

```java
// Java program to demonstrate
// the above function

import java.nio.charset.*;
import java.util.Iterator;
import java.util.Map;

public class GFG {

public static void main(String[] args)
    {

// Gets the charset
        Charset charset = Charset.forName("x-windows-949");

// Get the CharsetDecoder
        CharsetDecoder decoder = charset.newDecoder();

// Prints the CharsetDecoder
        System.out.println("CharsetDecoder: " + decoder);

try {
            System.out.println("detected Charset: "
                               + decoder.detectedCharset());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

## 输出

```java
CharsetDecoder: sun.nio.cs.ext.DoubleByte$Decoder@232204a1
java.lang.UnsupportedOperationException
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/nio/charset/CharsetDecoder.html#detectedCharset--](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/CharsetDecoder.html#detectedCharset--)