# 用示例描述 Java 中的 `getEndIndex()` 方法

> 原文：[https://www.geeksforgeeks.org/characteriterator-getendindex-method-in-java-with-examples/](https://www.geeksforgeeks.org/characteriterator-getendindex-method-in-java-with-examples/)

`getEndIndex()` 方法是 Java 中 `CharacterIterator` 接口的一部分，用于获取此迭代器要读取的结尾索引。此方法返回该索引号。

## 语法

```java
public int getEndIndex()
```

## 参数
此方法不接受任何参数。

## 返回值
该方法返回由该迭代器读取的结尾索引号。

## 异常
这个方法不抛出任何异常。

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

        System.out.println("Current EndIndex: "
                           + characterIterator
                                 .getEndIndex());
    }
}
```

## 输出

```java
Current EndIndex: 13
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#getEndIndex--](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#getEndIndex--)