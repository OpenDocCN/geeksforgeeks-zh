# Java 中的 CharsetEncoder malformedInputAction() 方法示例

> 原文：[https://www.geeksforgeeks.org/charsetencoder-malformedinputaction-method-in-java-with-examples/](https://www.geeksforgeeks.org/charsetencoder-malformedinputaction-method-in-java-with-examples/)

`malformedInputAction()` 方法是 `java.nio.charset.CharsetEncoder` 的内置方法，返回该编码器当前针对格式错误输入错误的操作。这样返回的 `CodingErrorAction` 有三种类型：`IGNORE`、`REPLACE` 和 `REPORT`。

## 语法

```java
public CodingErrorAction malformedInputAction()
```

## 参数

该方法不接受任何参数。

## 返回值

该方法返回当前的畸形输入动作，永不为空。

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

        // Prints CodingErrorAction
        System.out.println(encoder.malformedInputAction());
    }
}
```

**输出：**

```java
REPORT
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

        // Prints CodingErrorAction
        System.out.println(encoder.malformedInputAction());
    }
}
```

**输出：**

```java
REPORT
```

**参考：** [https://docs.oracle.com/javase/10/docs/api/java/nio/charset/CharsetEncoder.html#malformedInputAction()](https://docs.oracle.com/javase/10/docs/api/java/nio/charset/CharsetEncoder.html#malformedInputAction())