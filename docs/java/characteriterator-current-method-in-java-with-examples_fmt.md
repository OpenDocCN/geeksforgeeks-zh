# 用示例描述 Java 中的 `CharacterIterator.current()` 方法

> 原文：[https://www.geeksforgeeks.org/characteriterator-current-method-in-java-with-examples/](https://www.geeksforgeeks.org/characteriterator-current-method-in-java-with-examples/)

`current()` 方法在 Java 的 `CharacterIterator` 接口中用于获取当前要被这个迭代器读取的字符。此方法返回当前字符。

**语法：**

```java
public char current()
```

**参数：** 此方法不接受任何参数。

**返回值：** 该方法返回当前字符，该字符将由该字符迭代器读取。

**异常：** 这个方法不抛出任何异常。

**程序：**

```java
// Java program to demonstrate
// the above method

import java.text.*;
import java.util.*;

public class CharacterIteratorDemo {
    public static void main(String[] args)
    {

        CharacterIterator characterIterator
            = new StringCharacterIterator(
                "GeeksForGeeks");

        System.out.println("Current character: "
                           + characterIterator
                                 .current());
    }
}
```

**输出：**

```java
Current character: G
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#current--](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#current--)