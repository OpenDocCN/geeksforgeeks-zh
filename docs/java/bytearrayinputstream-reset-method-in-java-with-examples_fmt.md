# Java 中的 `ByteArrayInputStream` `reset()` 方法示例

> 原文：[https://www.geeksforgeeks.org/bytearrayinputstream-reset-method-in-java-with-examples/](https://www.geeksforgeeks.org/bytearrayinputstream-reset-method-in-java-with-examples/)

`reset()` 方法是由 `mark()` 方法调用的内置方法。它将输入流重新定位到标记的位置。

**语法**：
```java
public void reset()
```

**参数**：该功能不接受任何参数。
**返回值**：函数不返回任何东西。

以下是上述功能的实现：

## 程序一

```java
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {
        byte[] buf = { 5, 6, 7, 8, 9 };

        // Create new byte array input stream
        ByteArrayInputStream exam
            = new ByteArrayInputStream(buf);

        // print bytes
        System.out.println(exam.read());
        System.out.println(exam.read());
        System.out.println(exam.read());

        // Use of reset() method :
        // repositioning the stream to marked positions.
        exam.reset();

        System.out.println("\nreset() invoked");
        System.out.println(exam.read());
        System.out.println(exam.read());
    }
}
```

**输出**：
```java
reset() invoked
```

## 程序二

```java
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {
        byte[] buf = { 1, 2, 3, 4 };

        // Create new byte array input stream
        ByteArrayInputStream exam
            = new ByteArrayInputStream(buf);

        // print bytes
        System.out.println(exam.read());
        System.out.println(exam.read());
        System.out.println(exam.read());

        exam.mark(1);

        // Use of reset() method :
        // repositioning the stream to marked positions.
        exam.reset();

        System.out.println("\nreset() invoked");
        System.out.println(exam.read());
        System.out.println(exam.read());
    }
}
```

**输出**：
```java
reset() invoked
```

**参考**：[https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayInputStream.html#reset()](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayInputStream.html#reset())