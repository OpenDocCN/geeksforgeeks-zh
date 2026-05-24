# 用示例描述 Java 中的 previous() 方法

> 原文: [https://www.geeksforgeeks.org/characteriterator-previous-method-in-java-with-examples/](https://www.geeksforgeeks.org/characteriterator-previous-method-in-java-with-examples/)

`previous()` 方法是 `CharacterIterator` 接口中的一个方法。该接口用于获取要读取的前一个字符。此方法将迭代器向后递减一个索引，并返回前一个字符。

## 语法

```java
public char previous()
```

## 参数

此方法不接受任何参数。

## 返回值

该方法返回将由该迭代器读取的前一个字符。

## 异常

此方法不抛出任何异常。

## 程序示例

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

        characterIterator.next();

        System.out.println("Current character: "
                           + characterIterator
                                 .current());

        System.out.println("Previous character: "
                           + characterIterator
                                 .previous());
    }
}
```

## 输出

```java
Current character: e
Previous character: G
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#previous--](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#previous--)