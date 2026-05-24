# Java 中的 Matcher.group(int) 方法示例

> 原文：[https://www.geeksforgeeks.org/matcher-groupint-method-in-java-with-examples/](https://www.geeksforgeeks.org/matcher-groupint-method-in-java-with-examples/)

`Matcher` 类的 `group(int group)` 方法用于从指定的组中获取已经完成的匹配结果的组索引。

## 语法

```java
public String group(int group)
```

## 参数

该方法取一个参数 `group`，该参数是需要匹配模式的组索引。

## 返回值

该方法返回指定组中第一个匹配字符的索引。

## 异常

此方法抛出：
*   如果尚未尝试匹配，或者如果先前的匹配操作失败，则抛出 `IllegalStateException`。
*   如果给定索引的模式中没有捕获组，则抛出 `IndexOutOfBoundsException`。

下面的例子说明了 `Matcher.group()` 方法：

### 例 1

```java
// Java code to illustrate group() method

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
            // Get the group matched using group() method
            System.out.println(matcher.group(1));
        }
    }
}
```

**Output:**

> Current Matcher: java.util.regex.Matcher[pattern=(G*s) region=0,13 lastmatch=]
> s
> s

### 例 2

```java
// Java code to illustrate group() method

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
            = "GFGFGFGFGFGFGFGFGFG";

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
            System.out.println(matcher.group(0));
        }
    }
}
```

**Output:**

> Current Matcher: java.util.regex.Matcher[pattern=(G*G) region=0,19 lastmatch=]
> G
> G
> G
> G
> G
> G
> G
> G
> G
> G

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#group-int-](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#group-int-)