# 使用正则表达式

从较大字符串中提取单引号括起来的字符串的 Java 程序

> 原文: [https://www.geeksforgeeks.org/java-program-to-extract-a-single-quote-enclosed-string-from-a-larger-string-using-regex/](https://www.geeksforgeeks.org/java-program-to-extract-a-single-quote-enclosed-string-from-a-larger-string-using-regex/)

**问题陈述:** 给定一个字符串，使用 Java Regex 提取用单引号(')括起来的子字符串。

Java regex 是一个用正则表达式进行模式匹配的 API。`java.util.regex` 是一个用于匹配字符序列与正则表达式指定模式的包，其中 `Pattern` 类的实例表示正则表达式，而 `Matcher` 的实例用于将给定模式与输入序列进行匹配。输入通过实现 `CharSequence` 接口的类提供，以便支持与来自各种输入源的字符进行匹配。不允许将空参数传递给任何类或接口，因为它会抛出一个名为 `NullPointerException` 的异常。因此可以得出结论，`java.util.regex` 包包含如下接口和类：

> *   `MatchResult`: 匹配操作的结果。
> *   `Matcher`: 通过解释 `Pattern` 对 `CharSequence` 进行匹配操作的引擎。
> *   `Pattern`: 正则表达式的编译表示。

## 插图

```java
Input  : "Out of this String required only is 'Geeks for Geeks' only'"
Output : Geeks for Geeks

Input  : "The data wanted is'Java Regex'"
Output : Java Regex
```

## 例子

### Java 代码示例

```java
// Java program to demonstrate extracting
// substring enclosed in single quotes

// Importing Matcher and Pattern class
// from regex class of java.util package
// Importing input output classes
import java.io.*;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Custom input
        String string1
            = "Out of this String I want 'Geeks for Geeks' only";

        // Desired custom output
        String string2
            = "The data that I want is'Java Regex'";

        // Paranthesis indicate it is a group and signifies
        // it can have substring enclosed in single quote
        Pattern p = Pattern.compile(".*'([^']*)'.*");

        // This method returns a pattern object

        // Calling matcher() method of pattern object
        // and passing input character sequence
        Matcher m1 = p.matcher(string1);
        Matcher m2 = p.matcher(string2);

        // Printing complete entered string 1
        System.out.println("String to be extracted : "
                           + string1);

        // Condition check using matches() method which
        // looks out for content if any in single quote
        if (m1.matches()) {

            // Print the required sub-string
            System.out.println("Extracted part         : "
                               + m1.group(1));
        }

        // New line
        System.out.println();

        // Printing complete entered string 2
        System.out.println("String to be extracted : "
                           + string2);

        // Condition check using matches() method which
        // looks out for content if any in single quote
        if (m2.matches()) {

            // Print the required sub-string
            System.out.println("Extracted part         : "
                               + m2.group(1));
        }
    }
}
```

## 输出

```java
String to be extracted : Out of this String I want 'Geeks for Geeks' only
Extracted part         : Geeks for Geeks

String to be extracted : The data that I want is'Java Regex'
Extracted part         : Java Regex
```