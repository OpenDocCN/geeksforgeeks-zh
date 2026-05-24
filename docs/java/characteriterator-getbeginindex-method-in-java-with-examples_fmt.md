# 用示例描述 Java 中的 `getBeginIndex()` 方法

> 原文：[https://www.geeksforgeeks.org/characteriterator-getbeginindex-method-in-java-with-examples/](https://www.geeksforgeeks.org/characteriterator-getbeginindex-method-in-java-with-examples/)

`getBeginIndex()` 方法是 `CharacterIterator` 接口的一部分。Java 中的 `CharacterIterator` 接口用来获取这个迭代器要读取的开头的索引。此方法返回该索引号。

## 语法

```java
public int getBeginIndex()
```

## 参数

此方法不接受任何参数。

## 返回值

该方法返回由该迭代器读取的开头的索引号。

## 异常

这个方法不抛出任何异常。

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

        System.out.println("BeginIndex: "
                           + characterIterator
                                 .getBeginIndex());
    }
}
```

## 输出

```java
BeginIndex: 0
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#getBeginIndex--](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#getBeginIndex--)