# Java Long.decode() 方法示例

> 原文: [https://www.geeksforgeks.org/java-long-decode-method-with-examples/](https://www.geeksforgeks.org/java-long-decode-method-with-examples/)

`java.lang.Long.decode()` 是 Java 中的一个内置函数，它将一个字符串解码成一个 `Long`。它接受十进制、十六进制和八进制数字。

## 语法

```java
public static Long decode(String number) throws NumberFormatException
```

**参数:**
`number` - 需要被解码成 `Long` 的数字字符串。

## 错误和异常

*   **NumberFormatException:** 如果字符串不包含可解析的长整型字符串，程序将抛出此异常。

## 返回

返回解码后的字符串。

## 程序 1

下面的程序演示了该功能的工作。

```java
// Java program to demonstrate
// of java.lang.Long.decode() method
import java.lang.Math;

class GFG {

    // driver code
    public static void main(String args[])
    {
        // demonstration of function
        Long l = new Long(14);
        String str = "54534";

        System.out.println("Number = "
                        + l.decode(str));
    }
}
```

**输出:**

```java
Number = 54534
```

## 程序 2

程序使用 `decode()` 函数演示转换。

```java
// Java program to demonstrate
// of java.lang.Long.decode() method
import java.lang.Math;

class GFG {

    // driver code
    public static void main(String args[])
    {
        // demonstration of conversions
        String decimal = "10"; // Decimal
        String hexa = "0XFF"; // Hexa
        String octal = "067"; // Octal

        // convert decimal val to number using decode() method
        Integer number = Integer.decode(decimal);
        System.out.println("Decimal [" + decimal + "] = " + number);

        number = Integer.decode(hexa);
        System.out.println("Hexa [" + hexa + "] = " + number);

        number = Integer.decode(octal);
        System.out.println("Octal [" + octal + "] = " + number);
    }
}
```

**输出:**

```java
Decimal [10] = 10
Hexa [0XFF] = 255
Octal [067] = 55
```

## 程序 3

程序演示错误和异常。

```java
// Java program to demonstrate
// of java.lang.Long.decode() method
import java.lang.Math;

class GFG {

    // driver code
    public static void main(String args[])
    {
        // demonstration of error and exception when
        // a non-parsable Long is passed

        String decimal = "1A";

        // throws an error
        Integer number = Integer.decode(decimal);
        System.out.println("string [" + decimal + "] = " + number);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.NumberFormatException: For input string: "1A"
    at java.lang.NumberFormatException.forInputString(NumberFormatException.java:65)
    at java.lang.Integer.parseInt(Integer.java:580)
    at java.lang.Integer.valueOf(Integer.java:740)
    at java.lang.Integer.decode(Integer.java:1197)
    at GFG.main(File.java:16)
```