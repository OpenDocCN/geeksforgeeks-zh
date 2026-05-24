# Java 中的 MessageFormat setFormatByArgumentIndex() 方法示例

> 原文：[https://www.geeksforgeeks.org/messageformat-setformatbyargumentindex-method-in-java-with-example/](https://www.geeksforgeeks.org/messageformat-setformatbyargumentindex-method-in-java-with-example/)

`java.text.MessageFormat` 类的 `setFormatByArgumentIndex()` 方法用于通过覆盖以前的模式，在消息格式对象的模式中的特定索引处设置新的格式元素。

## 语法

```java
public void setFormatByArgumentIndex(int argumentIndex,
                                     Format newFormat)
```

## 参数

该方法以下列参数为参数。

*   `argumentIndex`：这是新格式元素将要放置的特定索引。
*   `newFormat`：这是将要放置的新格式元素。

## 返回值

这个方法没有什么可返回的。

以下举例说明 `setFormatByArgumentIndex()` 方法：

## 示例 1

```java
// Java program to demonstrate
// setFormatByArgumentIndex() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing MessageFormat
        MessageFormat mf
            = new MessageFormat("{1, date, #}, {3, number, #.##}, {5, time}");

        // display the current pattern
        System.out.println("old pattern : "
                           + mf.toPattern());

        // getting all the format element
        // used in MessageFormat Object
        Format[] formats = mf.getFormatsByArgumentIndex();

        // setting the new format element
        // at particular index
        // using setFormatByArgumentIndex() method
        for (int i = 0; i < formats.length; i++)
            mf.setFormatByArgumentIndex(i, formats[1]);

        // display the result
        System.out.println("\nnew pattern : "
                           + mf.toPattern());
    }
}
```

**输出：**

```java
old pattern : {1,date, #}, {3,number, #0.##}, {5,time}

new pattern : {1,date, #}, {3,date, #}, {5,date, #}
```

## 示例 2

```java
// Java program to demonstrate
// setFormatByArgumentIndex() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing MessageFormat
        MessageFormat mf
            = new MessageFormat("{1, date, #}, {3, number, #.##}, {5, time}");

        // display the current pattern
        System.out.println("old pattern : "
                           + mf.toPattern());

        // creating and initializing new Format element
        Format fm = NumberFormat.getInstance();

        // setting the new format element
        // at particular index
        // using setFormatByArgumentIndex() method
        for (int i = 0; i < 6; i++)
            mf.setFormatByArgumentIndex(i, fm);

        // display the result
        System.out.println("\nnew pattern : "
                           + mf.toPattern());
    }
}
```

**输出：**

```java
old pattern : {1,date, #}, {3,number, #0.##}, {5,time}

new pattern : {1,number}, {3,number}, {5,number}
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#setFormatByArgumentIndex-int-java.text.Format-](https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#setFormatByArgumentIndex-int-java.text.Format-)