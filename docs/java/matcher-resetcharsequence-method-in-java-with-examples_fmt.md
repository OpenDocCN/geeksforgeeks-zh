# Java 中的 Matcher.reset(CharSequence) 方法示例

> 原文：[https://www.geeksforgeeks.org/matcher-resetcharsequence-method-in-java-with-examples/](https://www.geeksforgeeks.org/matcher-resetcharsequence-method-in-java-with-examples/)

`Matcher` 类的 `reset(CharSequence input)` 方法用于重置该匹配器，并将作为参数传递的输入字符串插入该匹配器。

## 语法

```java
public Matcher reset(CharSequence input)
```

## 参数

该方法取参数 `input`，即复位后要插入匹配器的字符串。

## 返回值

此方法用此输入复位后返回此 `Matcher`。

以下示例说明了 `Matcher.reset()` 方法：

## 示例 1

```java
// Java code to illustrate reset() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "Geeks";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched = "GeeksForGeeks";

        // Create a matcher for the input String
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the current matcher state
        System.out.println("Current Matcher: "
                           + matcher.toMatchResult());

        // Reset the Matcher using reset() method
        String newStringToBeMatched
            = "GeeksGeeksGeeks";
        matcher = matcher
                      .reset(newStringToBeMatched);

        // Get the current matcher state
        System.out.println("Current Matcher after Reset: "
                           + matcher.toMatchResult());
    }
}
```

**输出：**

> Current Matcher: java.util.regex.Matcher[pattern=Geeks region=0,13 lastmatch=]
> Current Matcher after Reset: java.util.regex.Matcher[pattern=Geeks region=0,15 lastmatch=]

## 示例 2

```java
// Java code to illustrate reset() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "GFG";

        // Create a pattern from regex
        Pattern pattern = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GFGFGFGFGFGFGFGFGFG";

        // Create a matcher for the input String
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the current matcher state
        System.out.println("Current Matcher: "
                           + matcher.toMatchResult());

        // Reset the Matcher using reset() method
        String newStringToBeMatched
            = "GFG means GeeksForGeeks";
        matcher = matcher
                      .reset(newStringToBeMatched);

        // Get the current matcher state
        System.out.println("Current Matcher after Reset: "
                           + matcher.toMatchResult());
    }
}
```

**输出：**

> Current Matcher: java.util.regex.Matcher[pattern=GFG region=0,19 lastmatch=]
> Current Matcher after Reset: java.util.regex.Matcher[pattern=GFG region=0,23 lastmatch=]

## 参考

[Oracle 文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#reset-java.lang.CharSequence-)