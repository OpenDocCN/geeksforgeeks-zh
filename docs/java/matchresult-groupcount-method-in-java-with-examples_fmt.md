# Java 中的 MatchResult groupCount()方法，带示例

> 原文：[https://www.geeksforgeeks.org/matchresult-groupcount-method-in-java-with-examples/](https://www.geeksforgeeks.org/matchresult-groupcount-method-in-java-with-examples/)

`MatchResult`接口的`groupCount()`方法用于获取该匹配器模式中的捕获组数量。此方法返回一个整数值，它是匹配此匹配器时找到的组数。

## 语法

```java
public int groupCount()
```

## 参数
该方法不取任何参数。

## 返回值
该方法返回该匹配器模式下的捕获组数。

以下示例说明了`MatchResult.groupCount()`方法：

### 示例 1

```java
// Java code to illustrate groupCount() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(Geeks)";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = " GeeksForGeeks Geeks for For Geeks Geek";

        // Create a matcher for the input String
        MatchResult matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the number of capturing groups
        // using groupCount() method
        System.out.println(matcher.groupCount());
    }
}
```

**Output:**

```java

```

### 示例 2

```java
// Java code to illustrate groupCount() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "GFG";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "FGF GF FG FGF";

        // Create a matcher for the input String
        MatchResult matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the number of capturing groups
        // using groupCount() method
        System.out.println(matcher.groupCount());
    }
}
```

**Output:**

```java

```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#groupCount--](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#groupCount--)