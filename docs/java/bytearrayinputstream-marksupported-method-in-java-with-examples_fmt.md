# Java 中 `ByteArrayInputStream` `markSupported()` 方法示例

> 原文：[https://www.geeksforgeeks.org/bytearrayinputstream-marksupported-method-in-java-with-examples/](https://www.geeksforgeeks.org/bytearrayinputstream-marksupported-method-in-java-with-examples/)

`markSupported()` 方法是 [`ByteArrayInputStream`](https://www.geeksforgeeks.org/io-bytearrayinputstream-class-java/) 类的内置方法，用于测试该输入流是否支持标记和重置方法。`ByteArrayInputStream` 的 `markSupported` 方法始终返回 `true`。

## 语法

```java
public boolean markSupported()
```

## 参数
该方法不接受任何参数。

## 返回值
该方法返回一个布尔值。如果此流实例支持标记和重置方法，则返回 `true`，否则返回 `false`。

下面是上述功能的实现：

## 程序 1

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

        System.out.println("Mark() invocation");

        // Use of markSupported
        boolean check = exam.markSupported();
        System.out.println("markSupported() : "
                           + check);

        if (exam.markSupported()) {

            // Use of reset() method :
            // repositioning the stream to marked positions.
            exam.reset();

            System.out.println("\nreset() invoked");
            System.out.println(exam.read());
            System.out.println(exam.read());
        }
        else {
            System.out.println("reset() method not supported.");
        }
    }
}
```

**输出：**

```java
Mark() invocation
markSupported() : true

reset() invoked
```

## 程序 2

```java
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {
        byte[] buf = { 1, 2, 3 };

        // Create new byte array input stream
        ByteArrayInputStream exam
            = new ByteArrayInputStream(buf);

        // print bytes
        System.out.println(exam.read());
        System.out.println(exam.read());
        System.out.println(exam.read());

        // Use of markSupported
        boolean check = exam.markSupported();

        System.out.println("markSupported() : "
                           + check);

        if (exam.markSupported()) {

            // Use of reset() method :
            // repositioning the stream to marked positions
            exam.reset();

            System.out.println("\nreset() invoked");
            System.out.println(exam.read());
            System.out.println(exam.read());
        }
        else {
            System.out.println("reset() method not supported.");
        }
    }
}
```

**输出：**

```java
markSupported() : true

reset() invoked
```

**参考：** [https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayInputStream.html#markSupported()](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayInputStream.html#markSupported())