# Java中的CharsetDecoder unmappableCharacterAction()方法，示例

> 原文：[CharsetDecoder unmappableCharacterAction() method in Java with Examples](https://www.geeksforgeeks.org/charsetdecoder-unmappablecharacteraction-method-in-java-with-examples/)

`unmappableCharacterAction()`方法是`java.nio.charset.CharsetDecoder`类的一个内置方法，该方法返回此解码器针对不可映射字符错误的当前操作。

## 语法

```java
public CodingErrorAction unmappableCharacterAction()
```

## 参数

该方法不接受任何参数。

## 返回值

对于不可映射的字符错误，该方法返回此解码器的当前动作。

下面是上述功能的实现：

## 程序1

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

        System.out.println("Current action for "
                           + "unmappable-character errors: "
                           + decoder.unmappableCharacterAction());
    }
}
```

## 输出

```java
CharsetDecoder: sun.nio.cs.ext.ISO2022_CN$Decoder@232204a1
Current action for unmappable-character errors: REPORT
```

## 程序2

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

        System.out.println("Current action for "
                           + "unmappable-character errors: "
                           + decoder.unmappableCharacterAction());
    }
}
```

## 输出

```java
CharsetDecoder: sun.nio.cs.ext.DoubleByte$Decoder@232204a1
Current action for unmappable-character errors: REPORT
```

## 参考

[CharsetDecoder.unmappableCharacterAction()](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/CharsetDecoder.html#unmappableCharacterAction--)