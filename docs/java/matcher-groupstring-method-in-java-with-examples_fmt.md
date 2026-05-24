# Java 中的 Matcher.group(String) 方法示例

> 原文：[`https://www.geeksforgeeks.org/matcher-groupstring-method-in-java-with-examples/`](https://www.geeksforgeeks.org/matcher-groupstring-method-in-java-with-examples/)

`Matcher` 类的 `group(String)` 方法用于从指定的字符串中获取已经完成的匹配结果的组。

## 语法

```java
public String group(String string)
```

## 参数

该方法取一个参数 `string`，即需要匹配模式的组索引的字符串。

## 返回值

该方法从指定字符串中返回匹配组的 `group`。

## 异常

此方法抛出：

*   如果尚未尝试匹配，或者如果先前的匹配操作失败，则 `IllegalStateException`。
*   如果给定名称的模式中没有捕获组，则 `IndexOutOfBoundsException`。

下面的例子说明了 `Matcher.group()` 方法：

### 例 1

```java
// Java code to illustrate end() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

// Get the regex to be checked
        String regex = "\\b(?<Geeks>[A-Za-z\\s]+)";

// Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

// Get the String to be matched
        String stringToBeMatched
            = "GeeksForGeeks";

// Create a matcher for the input String
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

// Get the current matcher state
        MatchResult result
            = matcher.toMatchResult();
        System.out.println("Current Matcher: "
                           + result);

while (matcher.find()) {
            // Get the group matched using group() method
            System.out.println(matcher.group("Geeks"));
        }
    }
}
```

**Output:**

> Current Matcher:java.util.regex.Matcher[pattern=\b(?<Geeks>[A-Za-z\s]+) region=0,13 lastmatch=]
> GeeksForGeeks

### 例 2

```java
// Java code to illustrate end() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

// Get the regex to be checked
        String regex = "\\b(?<GFG>[A-Za-z\\s]+)";

// Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

// Get the String to be matched
        String stringToBeMatched
            = "GFG FGF GFG";

// Create a matcher for the input String
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

// Get the current matcher state
        MatchResult result
            = matcher.toMatchResult();
        System.out.println("Current Matcher: "
                           + result);

while (matcher.find()) {
            // Get the group matched using group() method
            System.out.println(matcher.group("GFG"));
        }
    }
}
```

**Output:**

> Current Matcher:java.util.regex.Matcher[pattern=\b(?<GFG>[A-Za-z\s]+) region=0,11 lastmatch=]
> GFG FGF GFG

## 参考

[`Oracle 文档`](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#group-java.lang.String-)