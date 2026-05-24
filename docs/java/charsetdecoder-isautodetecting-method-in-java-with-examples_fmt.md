# CharsetDecoder 中的 isAutoDetecting() 方法示例

> 原文: [https://www.geeksforgeeks.org/charsetdecoder-isautodetecting-method-in-java-with-examples/](https://www.geeksforgeeks.org/charsetdecoder-isautodetecting-method-in-java-with-examples/)

`isAutoDetecting()` 方法是 `java.nio.charset.CharsetDecoder` 类的内置方法，它告诉这个解码器是否实现了自动检测字符集。

## 语法

```java
public boolean isAutoDetecting()
```

## 参数

该方法不接受任何参数。

## 返回值

该方法返回一个布尔值，说明该字符集解码器是否实现了自动检测字符集。

下面是上述功能的实现：

### 程序 1

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

        System.out.println("Is CharsetDecoder auto-detecting: "
                           + decoder.isAutoDetecting());
    }
}
```

**输出:**

```java
CharsetDecoder: sun.nio.cs.ext.ISO2022_CN$Decoder@232204a1
Is CharsetDecoder auto-detecting: false
```

### 程序 2

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

        System.out.println("Is CharsetDecoder auto-detecting: "
                           + decoder.isAutoDetecting());
    }
}
```

**输出:**

```java
CharsetDecoder: sun.nio.cs.ext.DoubleByte$Decoder@232204a1
Is CharsetDecoder auto-detecting: false
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/nio/charset/CharsetDecoder.html#isAutoDetecting--](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/CharsetDecoder.html#isAutoDetecting--)