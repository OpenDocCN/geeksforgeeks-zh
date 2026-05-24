# ByteArrayInputStream 的 available() 方法在 Java 中的使用示例

> 原文：[https://www.geeksforgeeks.org/bytearrayinputstream-available-method-in-java-with-examples/](https://www.geeksforgeeks.org/bytearrayinputstream-available-method-in-java-with-examples/)

`available()` 方法是 [`ByteArrayInputStream`](https://www.geeksforgeeks.org/io-bytearrayinputstream-class-java/) 的内置方法，返回可以从此输入流中读取（或跳过）的剩余字节数。它告知要从输入流中读取的字节总数。

**语法**：

```java
public int available()
```

**参数**：该方法不接受任何参数。
**返回值**：该方法返回输入流中要读取的字节总数。

下面是上述功能的实现：

**程序 1：**

## Java 语言示例

```java
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {

        // Array
        byte[] buffer = { 71, 69, 69, 75, 83 };

        // Create InputStream
        ByteArrayInputStream geek
            = new ByteArrayInputStream(buffer);

        // Use the function to get the number
        // of available
        int number = geek.available();

        // Print
        System.out.println("Use of available() method : "
                           + number);
    }
}
```

**Output：**

```java
Use of available() method : 5
```

**程序 2：**

## Java 语言示例

```java
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {

        // Array
        byte[] buffer = { 1, 2, 3, 4 };

        // Create InputStream
        ByteArrayInputStream geek
            = new ByteArrayInputStream(buffer);

        // Use the function to get the number
        // of available
        int number = geek.available();

        // Print
        System.out.println("Use of available() method : "
                           + number);
    }
}
```

**Output：**

```java
Use of available() method : 4
```

**参考：**[https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayInputStream.html#available()](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayInputStream.html#available())