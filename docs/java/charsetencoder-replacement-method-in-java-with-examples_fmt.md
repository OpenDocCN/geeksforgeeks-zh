# Java 中的 CharsetEncoder replacement() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/charsetencoder-replacement-method-in-java-with-examples/](https://www.geeksforgeeks.org/charsetencoder-replacement-method-in-java-with-examples/)

`replacement()` 方法是 `java.nio.charset.CharsetEncoder` 的内置方法，返回一个字节数组作为编码器的替换值。

## 语法

```java
public final byte[] replacement()
```

## 参数

该功能不接受任何参数。

## 返回值

该函数返回该编码器当前的替换值，永不为空。

下面是上述功能的实现：

### 程序 1

```java
// Java program to implement
// the above function
import java.nio.CharBuffer;
import java.nio.charset.Charset;
import java.nio.charset.CharsetEncoder;

public class Main {
    public static void main(String[] args) throws Exception
    {
        // Gets the encoder
        CharsetEncoder encoder = Charset.forName("UTF16").newEncoder();

        // Prints byte array representing
        // the replacement value
        System.out.println(encoder.replacement());
    }
}
```

**输出：**

```java
[B@232204a1
```

### 程序 2

```java
// Java program to implement
// the above function
import java.nio.CharBuffer;
import java.nio.charset.Charset;
import java.nio.charset.CharsetEncoder;

public class Main {
    public static void main(String[] args) throws Exception
    {
        // Gets the encoder
        CharsetEncoder encoder = Charset.forName("US-ASCII").newEncoder();

        // Prints byte array representing
        // the replacement value
        System.out.println(encoder.replacement());
    }
}
```

**输出：**

```java
[B@232204a1
```

**参考：** [https://docs.oracle.com/javase/10/docs/api/java/nio/charset/CharsetEncoder.html#replacement()](https://docs.oracle.com/javase/10/docs/api/java/nio/charset/CharsetEncoder.html#replacement())