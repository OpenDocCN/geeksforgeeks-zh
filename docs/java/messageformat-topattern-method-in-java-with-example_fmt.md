# Java中的MessageFormat.toPattern()方法示例

> 原文：[`https://www.geeksforgeeks.org/messageformat-topattern-method-in-java-with-example/`](https://www.geeksforgeeks.org/messageformat-topattern-method-in-java-with-example/)

`java.text.MessageFormat`类的`toPattern()`方法用于获取该消息格式对象的当前模式的字符串表示。

## 语法

```java
public String toPattern()
```

## 参数

该方法不接受任何参数。

## 返回值

此方法返回此`MessageFormat`对象当前模式的字符串表示。

以下是说明`toPattern()`方法的示例：

## 示例1

### Java代码

```java
// Java program to demonstrate
// toPattern() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{0, number, #}, {2, date, #.#}, {4, time}");

        // getting the pattern
        // of this MessageFormat Object
        // using toPattern() method
        String patt = mf.toPattern();

        // display the result
        System.out.println("current pattern of MessageFormat Object : " + patt);
    }
}
```

### 输出

```java
current pattern of MessageFormat Object : {0, number, #}, {2, date, #.#}, {4, time}
```

## 示例2

### Java代码

```java
// Java program to demonstrate
// toPattern() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{0, number, #}, {4, time}");

        // getting the pattern
        // of this MessageFormat Object
        // using toPattern() method
        String patt = mf.toPattern();

        // display the result
        System.out.println("current pattern of MessageFormat Object : " + patt);
    }
}
```

### 输出

```java
current pattern of MessageFormat Object : {0, number, #}, {4, time}
```

## 参考

[`https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#toPattern--`](https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#toPattern--)