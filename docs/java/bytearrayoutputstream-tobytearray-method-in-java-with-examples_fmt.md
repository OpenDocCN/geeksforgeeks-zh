# Java ByteArrayOutputStream toByteArray() 方法详解与示例

> 原文：[https://www.geeksforgeeks.org/bytearrayoutputstream-tobytearray-method-in-java-with-examples/](https://www.geeksforgeeks.org/bytearrayoutputstream-tobytearray-method-in-java-with-examples/)

Java 中的 `ByteArrayOutputStream` 类的 `toByteArray()` 方法用于创建一个新的、已分配的字节数组。新分配的字节数组的大小等于该输出流的当前大小。此方法将缓冲区的有效内容复制到其中。

## 语法
```java
public byte[] toByteArray()
```

## 参数
此方法不接受任何参数。

## 返回值
该方法返回一个新分配的字节数组，该数组包含此输出流的有效内容。

## 异常
此方法不抛出任何异常。

下面的程序举例说明了 `java.io` 包中 `ByteArrayOutputStream` 类中的 `toByteArray()` 方法：

## 程序 1
```java
// Java program to illustrate
// ByteArrayOutputStream toByteArray() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws Exception
    {
        // Create byteArrayOutputStream
        ByteArrayOutputStream byteArrayOutStr
            = new ByteArrayOutputStream();

        // Create byte array
        byte[] buf = { 71, 69, 69, 75, 83 };

        // Write byte array
        // to byteArrayOutputStream
        byteArrayOutStr.write(buf);

        for (byte b : byteArrayOutStr
                          .toByteArray()) {
            // Print the byte
            System.out.println((char)b);
        }
    }
}
```

### Output
```java
G
E
E
K
S
```

## 程序 2
```java
// Java program to illustrate
// ByteArrayOutputStream toByteArray() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws Exception
    {
        // Create byteArrayOutputStream
        ByteArrayOutputStream byteArrayOutStr
            = new ByteArrayOutputStream();

        // Create byte array
        byte[] buf = { 71, 69, 69, 75, 83,
                       70, 79, 82, 71, 69,
                       69, 75, 83 };

        // Write byte array
        // to byteArrayOutputStream
        byteArrayOutStr.write(buf);

        for (byte b : byteArrayOutStr
                          .toByteArray()) {
            // Print the byte
            System.out.println((char)b);
        }
    }
}
```

### Output
```java
G
E
E
K
S
F
O
R
G
E
E
K
S
```

## 参考资料
[https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayOutputStream.html#toByteArray()](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayOutputStream.html#toByteArray())