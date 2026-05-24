# Java中的`Charset.name()`方法，带示例

> 原文：[`https://www.geeksforgeeks.org/charset-name-method-in-java-with-examples/`](https://www.geeksforgeeks.org/charset-name-method-in-java-with-examples/)

`name()`方法是`java.nio.charset`包的内置方法，返回字符集的规范名称。

## 语法

```java
public final String name()
```

## 参数

该方法不接受任何参数。

## 返回值

该方法返回字符集的规范名称。

下面是上述功能的实现：

### 程序1

```java
// Java program to demonstrate
// the above function

import java.nio.charset.Charset;
import java.nio.charset.CharsetDecoder;
import java.nio.charset.CharsetEncoder;

public class GFG {

    public static void main(String[] args)
    {
        // Gets charset
        Charset Charset1 = Charset.forName("UTF8");

        // Prints it
        System.out.println(Charset1.name());
    }
}
```

**输出：**

```
UTF-8
```

### 程序2

```java
// Java program to demonstrate
// the above function

import java.nio.charset.Charset;
import java.nio.charset.CharsetDecoder;
import java.nio.charset.CharsetEncoder;

public class GFG {

    public static void main(String[] args)
    {
        // Gets charset
        Charset Charset1 = Charset.forName("UTF16");

        // Prints it
        System.out.println(Charset1.name());
    }
}
```

**输出：**

```
UTF-16
```

**参考：** [`https://docs.oracle.com/javase/9/docs/api/java/nio/charset/Charset.html#name--`](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/Charset.html#name--)