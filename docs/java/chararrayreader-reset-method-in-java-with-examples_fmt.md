# Java中CharArrayReader reset()方法示例

> 原文：[https://www.geeksforgeeks.org/chararrayreader-reset-method-in-java-with-examples/](https://www.geeksforgeeks.org/chararrayreader-reset-method-in-java-with-examples/)

Java中 [`CharArrayReader`](https://www.geeksforgeeks.org/java-io-chararrayreader-class-java/) 类的 [`reset()`](https://www.geeksforgeeks.org/java-io-chararrayreader-class-java/) 方法用于重置流。重置后，如果流已被标记，则此方法尝试在标记处重新定位它，否则它将尝试将其定位到起点。

## 语法

```java
public void reset()
```

## 参数

该方法不接受任何参数。

## 返回值

此方法不返回值。

## 异常

如果输入输出时出现错误，此方法会抛出 `IOException`：
*   如果流未被标记。
*   如果标记无效。
*   如果不支持 `reset()` 方法。

下面的方法说明了 [`reset()`](https://www.geeksforgeeks.org/java-io-chararrayreader-class-java/) 方法的工作原理：

## 程序 1

```java
// Java program to demonstrate
// CharArrayReader reset() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            char[] str = { 'G', 'e', 'e', 'k', 's',
                           'F', 'o', 'r',
                           'G', 'e', 'e', 'k', 's' };

            // Create a CharArrayReader instance
            CharArrayReader reader
                = new CharArrayReader(str);

            // Get the character
            // to be read from the stream
            int ch;

            // Read the first 10 characters
            // to this reader using read() method
            // This will put the str in the stream
            // till it is read by the reader
            for (int i = 0; i < 10; i++) {
                ch = reader.read();
                System.out.print((char)ch);
            }

            System.out.println();

            // mark the stream for
            // 5 characters using reset()
            reader.mark(5);

            // reset the stream position
            reader.reset();

            // Read the 5 characters from marked position
            // to this reader using read() method
            for (int i = 0; i < 5; i++) {
                ch = reader.read();
                System.out.print((char)ch);
            }
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

## 输出

```
GeeksForGe
eks??
```

## 程序 2

```java
// Java program to demonstrate
// CharArrayReader reset() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {
            char[] str = { 'G', 'e', 'e', 'k', 's',
                           'F', 'o', 'r',
                           'G', 'e', 'e', 'k', 's' };

            // Create a CharArrayReader instance
            CharArrayReader reader
                = new CharArrayReader(str);

            // Get the character
            // to be read from the stream
            int ch;

            // Read the first 10 characters
            // to this reader using read() method
            // This will put the str in the stream
            // till it is read by the reader
            for (int i = 0; i < 10; i++) {
                ch = reader.read();
                System.out.print((char)ch);
            }

            System.out.println();

            // reset the stream position
            reader.reset();

            // Read the 5 characters from marked position
            // to this reader using read() method
            for (int i = 0; i < 5; i++) {
                ch = reader.read();
                System.out.print((char)ch);
            }
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

## 输出

```
GeeksForGe
Geeks
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/io/CharArrayReader.html#reset--](https://docs.oracle.com/javase/9/docs/api/java/io/CharArrayReader.html#reset--)