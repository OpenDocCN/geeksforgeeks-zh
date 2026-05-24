# 如何用 `String.matches()` 代替 Java 中的 `startsWith()` 方法？

> 原文: [https://www.geeksforgeeks.org/how-to-use-string-matches-as-a-substitute-of-startwith-method-in-java/](https://www.geeksforgeeks.org/how-to-use-string-matches-as-a-substitute-of-startwith-method-in-java/)

如语法所示，这个方法存在于 [`String`](https://www.geeksforgeeks.org/string-class-in-java/) 类中，该类负责测试一个字符串是否以从第一个索引开始的指定前缀开始。

## 语法

```java
public boolean startsWith(String prefix)
```

## 参数
要匹配的前缀。

## 返回值
如果参数表示的字符序列是该字符串表示的字符序列的前缀，则返回 `true` 否则为假。

## 方法
`startsWith()` 有两种替代品，如下所示:

1.  正则表达式
2.  `matches()` 方法

让我们讨论以下两种方法:

### 方法 1: 使用正则表达式

正则表达式 (简称 Regex) 是一个定义字符串模式的应用编程接口，可用于在 Java 中搜索、操作和编辑字符串。电子邮件验证和密码是字符串的几个领域，Regex 被广泛用于定义约束。正则表达式在 `java.util.regex` 包下提供。这包括 3 个类和 1 个接口。`java.util.regex` 包主要由以下三个类组成，如下表所示:

*   `Pattern`
*   `Matcher`
*   [`PatternSyntaxException`](https://www.geeksforgeeks.org/regular-expressions-in-java/)

#### 示例

```java
// java Program to Illustrate Usage of Regular Expressions
// as a Substitute of startWith() method

// Importing Matcher and Pattern classes
// from the java.util.regex package
import java.util.regex.Matcher;
import java.util.regex.Pattern;

// Main class
public class GFG {

// Main driver method
    public static void main(String args[])
    {
        // Declaring and initialising custom string
        String Str = new String("Welcome to geeksforgeeks");

// Display message for better readability
        System.out.print(
            "Check whether string starts with Welcome using startsWith : ");

// Testing the prefix using startsWith()
        System.out.println(Str.startsWith("Welcome"));

// Testing the prefix using Regex() by creating
        // objects of Pattern and Matcher class
        Pattern pattern = Pattern.compile("Welcome.*");
        Matcher m = pattern.matcher(Str);

// Print commands
        System.out.print(
            "Check whether string starts with Welcome using Regex: ");
        System.out.println(m.find() ? "true" : "false");
    }
}
```

#### 输出

```java
Check whether string starts with Welcome using startsWith : true
Check whether string starts with Welcome using Regex: true
```

### 方法 2: 使用 `String` 类的 `matches()` 方法

[`String.matches()`](https://www.geeksforgeeks.org/java-lang-string-matches-java/) 方法告诉这个字符串是否匹配给定的正则表达式。调用表单的这个方法会产生与表达式 `Pattern.matches(regex, string)` 完全相同的结果。

#### 语法

```java
public boolean matches(String regex)
```

#### 参数
该字符串要匹配的正则表达式。

#### 返回值
当且仅当该字符串与给定的正则表达式匹配时，该方法返回 `true`。

#### 示例

```java
// java Program to Illustrate Usage of String.matches()
// as a Substitute of startWith() method

// Importing required classes
import java.util.*;

// Main class
public class GFG {

// Main driver method
    public static void main(String args[])
    {
        // Declaring and initialising string
        String Str = new String("Welcome to geeksforgeeks");

// Testing the prefix using startsWith()
        // Work taken - 'Welcome'
        System.out.print(
            "Check whether string starts with Welcome using startsWith : ");
        System.out.println(Str.startsWith("Welcome"));

// Testing the prefix using Regex()
        // Word to be matched - 'Welcome'
        System.out.print(
            "Check whether string starts with Welcome using Matches: ");
        System.out.println(Str.matches("Welcome(.*)"));
    }
}
```

#### 输出

```java
Check whether string starts with Welcome using startsWith : true
Check whether string starts with Welcome using Matches: true
```