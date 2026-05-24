# Java 中的 `Character.isJavaIdentifierStart()` 方法

> 原文：[https://www.geeksforgeeks.org/character-isjavaidentifierstart-method-in-java-2/](https://www.geeksforgeeks.org/character-isjavaidentifierstart-method-in-java-2/)

`java.lang.Character.isJavaIdentifierStart(char ch)` 是 Java 中的一个内置方法，它确定指定的字符是否允许作为 Java 标识符中的第一个字符。当且仅当下列条件之一为真时，字符可以作为 Java 标识符开始：

*   `isLetter(ch)` 返回 `true`
*   `getType(ch)` 返回 `LETTER_NUMBER`
*   `ch` 是一个货币符号（例如 `'$'`）
*   `ch` 是一个标点符号（例如 `'_'`）。

## 注意
此方法不能处理补充字符。要支持所有的 Unicode 字符，包括补充字符，请使用 `isJavaIdentifierStart(int)` 方法。

## 语法
```java
public static boolean isJavaIdentifierStart(char ch)
```

## 参数
该函数接受一个强制参数 `ch`，用于指定要测试的字符。

## 返回值
这个方法返回一个布尔值。如果字符可能以 Java 标识符开头，布尔值为 `true`，否则为 `false`。

下面的程序演示了 `Character.isJavaIdentifierStart(char ch)` 方法：

## 程序 1
```java
// Java program to demonstrate the
// Character.isJavaIdentifierStart()
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {
        // create 2 char primitives c1, c2
        char c1 = '9', c2 = '-';

        // assign isJavaIdentifierStart results of c1, c2
        // to boolean primitives  bool1, bool2
        boolean bool1 = Character.isJavaIdentifierStart(c1);
        System.out.println(c1 + " may start a Java identifier is : " + bool1);

        boolean bool2 = Character.isJavaIdentifierStart(c2);
        System.out.println(c2 + " may start a Java identifier is : " + bool2);
    }
}
```

## 输出
```java
9 may start a Java identifier is : false
- may start a Java identifier is : false
```

## 程序 2
```java
// Java program to demonstrate the
// Character.isJavaIdentifierStart()

import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {
        // create 2 char primitives c1, c2
        char c1 = '5', c2 = '_';

        // assign isJavaIdentifierStart results of c1, c2
        // to boolean primitives  bool1, bool2
        boolean bool1 = Character.isJavaIdentifierStart(c1);
        System.out.println(c1 + " may start a Java identifier is : " + bool1);

        boolean bool2 = Character.isJavaIdentifierStart(c2);
        System.out.println(c2 + " may start a Java identifier is : " + bool2);
    }
}
```

## 输出
```java
5 may start a Java identifier is : false
_ may start a Java identifier is : true
```

## 参考
[https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isJavaIdentifierStart(char)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isJavaIdentifierStart(char))