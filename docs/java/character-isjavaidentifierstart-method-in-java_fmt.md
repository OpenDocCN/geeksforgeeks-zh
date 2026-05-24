# Java 中的 `Character.isJavaIdentifierStart()` 方法

> 原文：[https://www.geeksforgeeks.org/character-isjavaidentifierstart-method-in-java/](https://www.geeksforgeeks.org/character-isjavaidentifierstart-method-in-java/)

`Character.isJavaIdentifierStart(int codePoint)` 是 Java 中的一个内置方法，用于确定字符（Unicode 代码点）是否允许作为 Java 标识符中的第一个字符。需要注意的是，当且仅当下列条件之一为真时，一个字符可以开始一个 Java 标识符：

*   `isLetter(ch)` 返回 `true`
*   `getType(ch)` 返回 `LETTER_NUMBER`
*   `ch` 是一个货币符号（例如 `"$"`）
*   `ch` 是一个连接标点符号（例如 `"_"`）。

**语法：**

```java
public static boolean isJavaIdentifierStart(int codePoint)
```

**参数：** 参数 `codePoint` 为整数类型，指的是要测试的字符（Unicode 码点）。

**返回值：** `Character` 类的 `isJavaIdentifierStart(int codePoint)` 方法，如果字符可能以 Java 标识符开头，则返回 `true`；否则为 `false`。

下面的程序说明了 `Character.isJavaIdentifierStart()` 方法：

**程序 1：**

```java
// Java program to illustrate
// Character.isJavaIdentifierStart() method
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Create 2 int primitives c1, c2
        int c1 = 0x0039, c2 = 0x004b, c3 = 0x0081;

        // Assign isJavaIdentifierPart results of
        // c1, c2 to boolean primitives bool1, bool2
        boolean bool1 = Character.isJavaIdentifierStart(c1);
        boolean bool2 = Character.isJavaIdentifierStart(c2);
        boolean bool3 = Character.isJavaIdentifierStart(c3);

        String str1 = "c1 may start a Java identifier is " + bool1;
        String str2 = "c2 may start a Java identifier is " + bool2;
        String str3 = "c3 may start a Java identifier is " + bool3;

        // Print bool1, bool2 values
        System.out.println(str1);
        System.out.println(str2);
        System.out.println(str3);
    }
}
```

**输出：**

```java
c1 may start a Java identifier is false
c2 may start a Java identifier is true
c3 may start a Java identifier is false
```

**程序 2：**

```java
// Java program to illustrate
// Character.isJavaIdentifierStart() method
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Create 2 int primitives c1, c2
        int c1 = 0x0034, c2 = 0x005a;

        // Assign isJavaIdentifierPart results of
        // c1, c2 to boolean primitives bool1, bool2
        boolean bool1 = Character.isJavaIdentifierStart(c1);
        boolean bool2 = Character.isJavaIdentifierStart(c2);

        String str1 = "c1 may start a Java identifier is " + bool1;
        String str2 = "c2 may start a Java identifier is " + bool2;

        // Print bool1, bool2 values
        System.out.println(str1);
        System.out.println(str2);
    }
}
```

**输出：**

```java
c1 may start a Java identifier is false
c2 may start a Java identifier is true
```

**参考：** [https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isJavaIdentifierStart(char)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isJavaIdentifierStart(char))