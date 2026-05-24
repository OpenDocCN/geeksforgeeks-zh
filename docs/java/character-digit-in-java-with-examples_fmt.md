# Java 中的 Character.digit()，示例

> 原文：[https://www.geeksforgeeks.org/character-digit-in-java-with-examples/](https://www.geeksforgeeks.org/character-digit-in-java-with-examples/)

`java.lang.Character.digit()` 是 Java 中的一个内置方法，它以指定的基数返回字符 `ch` 的数值。如果基数不在范围 `MIN_RADIX <= radix <= MAX_RADIX` 内，或者如果 `ch` 的值不是指定基数中的有效数字，则返回 `-1`。如果以下至少一项为真，则字符为有效数字：

*   该方法对此字符为真，并且此字符的 Unicode 十进制数字值（或其单字符分解）小于指定的基数。在这种情况下，返回十进制数值。
*   该字符是大写拉丁字母 `'A'` 到 `'Z'` 之一，并且其代码小于 `radix + 'A' - 10`。在这种情况下，返回 `ch - 'A' + 10`。
*   该字符是小写拉丁字母 `'a'` 到 `'z'` 之一，并且其代码小于 `radix + 'a' - 10`。在这种情况下，返回 `ch - 'a' + 10`。
*   该字符是全角拉丁字母 `A` (`'\uFF21'`) 到 `Z` (`'\uFF3A'`) 之一，并且其代码小于 `radix + '\uFF21' - 10`。在这种情况下，返回 `ch - '\uFF21' + 10`。
*   该字符是全角小写拉丁字母 `a` (`'\uFF41'`) 到 `z` (`'\uFF5A'`) 之一，并且其代码小于 `radix + '\uFF41' - 10`。在这种情况下，返回 `ch - '\uFF41' + 10`。

## 语法：

```java
public static int digit(char ch, int radix)
```

## 参数：

该函数接受两个参数，如下所述：

*   `ch` - 这是指定要转换的字符的强制参数。
*   `radix` - 这是指定基数的强制参数。

## 返回值：

该方法返回指定基数的字符所代表的数值。

以下程序演示了上述方法：

## 程序 1：

```java
// Java program to illustrate the
// Character.digit() method

import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {
        // create and assign value
        // to 2 character objects
        char c1 = '3', c2 = '6';

        // assign the numeric value of c1 to in1 using radix
        int in1 = Character.digit(c1, 5);
        System.out.println("Numeric value of " + c1 + " in radix 5 is " + in1);

        // assign the numeric value of c2 to in2 using radix
        int in2 = Character.digit(c2, 15);
        System.out.println("Numeric value of " + c2 + " in radix 15 is " + in2);
    }
}
```

**Output:**

```java
Numeric value of 3 in radix 5 is 3
Numeric value of 6 in radix 15 is 6
```

## 程序 2：

```java
// Java program to illustrate the
// Character.digit() method
// when -1 is returned
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {
        // create and assign value
        // to 2 character objects
        char c1 = 'a', c2 = 'z';

        // assign the numeric value of c1 to in1 using radix
        int in1 = Character.digit(c1, 5);
        System.out.println("Numeric value of " + c1 + " in radix 5 is " + in1);

        // assign the numeric value of c2 to in2 using radix
        int in2 = Character.digit(c2, 15);
        System.out.println("Numeric value of " + c2 + " in radix 15 is " + in2);
    }
}
```

**Output:**

```java
Numeric value of a in radix 5 is -1
Numeric value of z in radix 15 is -1
```

## 参考：

[https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#digit(char,%20int)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#digit(char,%20int))