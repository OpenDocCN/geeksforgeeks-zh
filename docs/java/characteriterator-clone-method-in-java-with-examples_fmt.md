# 用示例描述 Java 中的 CharacterIterator.clone() 方法

> 原文: [https://www.geeksforgeeks.org/characteriterator-clone-method-in-java-with-examples/](https://www.geeksforgeeks.org/characteriterator-clone-method-in-java-with-examples/)

`clone()` 方法是 Java 中 `CharacterIterator` 接口的一部分，用于克隆这个 `CharacterIterator`。这意味着此方法将创建另一个具有与此 `CharacterIterator` 相同的所有属性的 `CharacterIterator` 实例，并返回它。

## 语法

```java
public Object clone()
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法返回一个 `Object`，它是这个 `CharacterIterator` 的克隆。

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

        String text = "GeeksForGeeks";

        CharacterIterator characterIterator
            = new StringCharacterIterator(text);

        System.out.println("Current CharacterIterator: "
                           + characterIterator);

        System.out.println("Cloned CharacterIterator: "
                           + characterIterator.clone());
    }
}
```

## 输出

```java
Current CharacterIterator: java.text.StringCharacterIterator@c11e1b98
Cloned CharacterIterator: java.text.StringCharacterIterator@c11e1b98
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#clone--](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#clone--)