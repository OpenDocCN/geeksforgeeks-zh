# Java 字符串 `toUpperCase()` 方法示例

> 原文：[https://www.geeksforgeeks.org/java-string-touppercase-method-with-examples/](https://www.geeksforgeeks.org/java-string-touppercase-method-with-examples/)

`String` 类的 `toUpperCase()` 方法用于将字符串的所有字符转换为大写字母。`toUpperCase()` 方法有两种变体。需要注意的关键点是，在使用默认区域设置时，其行为与 `toUpperCase(Locale.getDefault())` 方法相同。

**语法：**

```java
public String toUpperCase(Locale loc)
```

```java
public String toUpperCase()
```

**参数：**

*   类型 1：要应用的区域设置值，用于转换所有字符。
*   类型 2：北美。

**返回类型：** 返回大写字母的字符串。

> **注意：** 小写转换使用给定[地区](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/)的规则。

**例 1：**

## Java 语言示例

```java
// Java Program to Demonstrate Working of toUpperCase()
// method

// Main class
class GFG {

// Main driver method
    public static void main(String args[])
    {

// Custom input string
        String str = "Welcome! to Geeksforgeeks";

// Converting above input string to
        // uppercase letters using UpperCase() method
        String strup = str.toUpperCase();

// Print the uppercased string
        System.out.println(strup);
    }
}
```

**输出**

```java
WELCOME! TO GEEKSFORGEEKS
```

**例 2：**

## Java 语言示例

```java
// Java program to demonstrate Working of toUpperCase()
// method of Locale class

// Importing Locale class from java.util package
import java.util.Locale;

// Main class
class GFG {

// Main driver method
    public static void main(String args[])
    {

// Custom input string
        String str = "Geeks for Geeks";

// Locales with the language "tr" for TURKISH
        //"en" for ENGLISH is created
        Locale TURKISH = Locale.forLanguageTag("tr");
        Locale ENGLISH = Locale.forLanguageTag("en");

// Converting string str to uppercase letter
        // using TURKISH and ENGLISH language
        String strup1 = str.toUpperCase(TURKISH);
        String strup2 = str.toUpperCase(ENGLISH);
        System.out.println(strup1);
        System.out.println(strup2);
    }
}
```

**输出**

```java
GEEKS FOR GEEKS
GEEKS FOR GEEKS
```