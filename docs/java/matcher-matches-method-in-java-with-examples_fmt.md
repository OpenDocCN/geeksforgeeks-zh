# Matcher.matches() 方法示例（Java）

> 原文：[https://www.geeksforgeeks.org/matcher-matches-method-in-java-with-examples/](https://www.geeksforgeeks.org/matcher-matches-method-in-java-with-examples/)

使用 `Matcher` 类的 `matches()` 方法，可以获取该模式是否与该匹配器匹配的结果。它返回一个布尔值，指示匹配是否成功。

## 语法

```java
public boolean matches()
```

## 参数
该方法不接受任何参数。

## 返回值
该方法返回一个 `boolean` 值，表示该模式是否与该匹配器匹配。

以下示例说明了 `Matcher.matches()` 方法：

### 示例 1

```java
// Java code to illustrate matches() method

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
        String stringToBeMatched
            = "GeeksForGeeks";

        // Create a matcher for the input String
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the result state
        // using matches() method
        System.out.println("Result: "
                           + matcher.matches());
    }
}
```

**输出：**

```java
Result: false
```

### 示例 2

```java
// Java code to illustrate matches() method

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
            = "GFGFGFGFGFGFGFGFGFG";

        // Create a matcher for the input String
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the result state
        // using matches() method
        System.out.println("Result: "
                           + matcher.matches());
    }
}
```

**输出：**

```java
Result: false
```

**参考：** [Oracle 文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#matches--)