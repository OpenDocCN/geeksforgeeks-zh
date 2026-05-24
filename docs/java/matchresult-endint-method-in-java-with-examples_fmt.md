# Java 中 MatchResult end(int) 方法示例

> 原文：[https://www.geeksforgeeks.org/matchresult-endint-method-in-java-with-examples/](https://www.geeksforgeeks.org/matchresult-endint-method-in-java-with-examples/)

`MatchResult` 接口的 `end(int group)` 方法用于从指定的组中获取已经完成的匹配结果的结束索引之后的偏移量。

## 语法

```java
public int end(int group)
```

## 参数

该方法接受一个参数 `group`，表示需要匹配图案结束索引后的偏移量。

## 返回值

该方法返回指定组匹配结束索引后的 `offset`。

## 异常

此方法抛出：
*   如果尚未尝试匹配，或者如果先前的匹配操作失败，则抛出 `IllegalStateException`。
*   如果给定组的模式中没有捕获组，则抛出 `IndexOutOfBoundsException`。

以下示例说明了 `MatchResult.end()` 方法：

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
        MatchResult matcher
            = pattern
                  .matcher(stringToBeMatched);

while (((Matcher)matcher).find()) {
            // Get the last index of match result
            System.out.println(matcher.end(1));
        }
    }
}
```

**输出：**

```java

```

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
        MatchResult matcher
            = pattern
                  .matcher(stringToBeMatched);

while (((Matcher)matcher).find()) {
            // Get the last index of match result
            System.out.println(matcher.end(0));
        }
    }
}
```

**输出：**

```java

```