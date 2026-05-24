# Java 中 Matcher end()方法，带示例

> 原文: [https://www.geeksforgeeks.org/matcher-end-method-in-java-with-examples/](https://www.geeksforgeeks.org/matcher-end-method-in-java-with-examples/)

`Matcher`类的`end()`方法用于获取匹配结果中最后一个匹配字符后的偏移量。

## 语法
```java
public int end()
```

## 参数
该方法不取任何参数。

## 返回值
该方法返回最后一个匹配字符后的偏移量。

## 异常
如果还没有尝试匹配，或者如果之前的匹配操作失败，此方法将抛出`IllegalStateException`。

以下示例说明了`Matcher.end()`方法:

## 示例 1
```java
// Java code to illustrate end() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(G*s)";

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
            // Get the last index of match result
            System.out.println(matcher.end());
        }
    }
}
```

**输出:**
> Current Matcher: `java.util.regex.Matcher[pattern=(G*s) region=0,13 lastmatch=]`
> 5
> 13

## 示例 2
```java
// Java code to illustrate end() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(G*G)";

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
            // Get the last index of match result
            System.out.println(matcher.end());
        }
    }
}
```

**输出:**
> Current Matcher: `java.util.regex.Matcher[pattern=(G*G) region=0,11 lastmatch=]`
> 1
> 3
> 6
> 9
> 11

## 参考
[Oracle 文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#end--)