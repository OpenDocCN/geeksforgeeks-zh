# 用示例描述 Java 中的 `last()` 方法

> 原文：[CharacterIterator last() method in Java with Examples](https://www.geeksforgeeks.org/characteriterator-last-method-in-java-with-examples/)

`last()` 方法是 [`CharacterIterator`](https://www.geeksforgeeks.org/tag/java-characteriterator/) 接口中的一个方法，属于 [Java 文本包](https://www.geeksforgeeks.org/tag/java-text-package/)。在 Java 中，此方法用于获取此迭代器结尾的字符。此方法使用 `getEndIndex()` 将迭代器的位置设置为最后一个字符，然后返回该字符。

## 语法

```java
public char last()
```

## 参数

此方法不接受任何参数。

## 返回值

此方法使用 `getEndIndex()`，将迭代器的位置设置为最后一个字符，然后返回那个字符。

## 异常

此方法不抛出任何异常。

## 程序

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

        System.out.println("Last character: "
                           + characterIterator
                                 .last());
    }
}
```

## 输出

```java
Current character: G
Last character: s
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#last--](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#last--)