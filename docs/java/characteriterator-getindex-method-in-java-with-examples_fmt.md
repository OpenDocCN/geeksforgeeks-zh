## 用示例描述 Java 中的 `getIndex()` 方法

> 原文：[https://www.geeksforgeeks.org/characteriterator-getindex-method-in-java-with-examples/](https://www.geeksforgeeks.org/characteriterator-getindex-method-in-java-with-examples/)

`getIndex()` 方法是 Java 中 `CharacterIterator` 接口的一部分，用于获取该迭代器当前要读取的字符的索引。此方法返回该索引号。

### 语法

```java
public int getIndex()
```

### 参数
此方法不接受任何参数。

### 返回值
该方法返回将由该迭代器读取的索引号。

### 异常
这个方法不抛出任何异常。

### 程序

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

        System.out.println("Current Index: "
                           + characterIterator
                                 .getIndex());
    }
}
```

### 输出

```java
Current character: G
Current Index: 0
```

### 参考
[https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#getIndex--](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#getIndex--)