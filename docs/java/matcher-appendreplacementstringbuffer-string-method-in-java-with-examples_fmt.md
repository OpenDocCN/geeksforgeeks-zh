# Java 中的 Matcher appendReplacement(StringBuffer, String) 方法，示例

> 原文：`https://www.geeksforgeeks.org/matcher-appendreplacementstringbuffer-string-method-in-java-with-examples/`

`Matcher` 类的 `appendReplacement(StringBuffer, String)` 方法表现为追加替换方法。此方法读取输入字符串，并用匹配器字符串中匹配的模式替换它。

## 语法

```java
public Matcher appendReplacement(StringBuffer buffer, String stringToBeReplaced)
```

## 参数

该方法取两个参数：

*   `buffer`：用于存储目标字符串的 `StringBuffer`。
*   `stringToBeReplaced`：要在匹配器中被替换的字符串。

## 返回值

该方法返回一个替换了目标字符串的 `Matcher`。

## 异常

此方法抛出以下异常：

*   `IllegalStateException`：如果尚未尝试匹配，或者之前的匹配操作失败。
*   `IllegalArgumentException`：如果替换字符串引用了模式中不存在的命名捕获组。
*   `IndexOutOfBoundsException`：如果替换字符串引用了模式中不存在的捕获组。

下面的例子说明了 `Matcher.appendReplacement()` 方法：

## 例 1

```java
// Java code to illustrate appendReplacement() method

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
            = "GeeksForGeeks Geeks for For Geeks Geek";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        System.out.println("Before Replacement: "
                           + stringToBeMatched);

        // Get the String to be replaced
        String stringToBeReplaced = "GEEKS";
        StringBuffer buffer = new StringBuffer();

        // Replace every matched pattern
        // with the target String
        // using appendReplacement() method
        while (matcher.find()) {
            matcher.appendReplacement(buffer,
                                      stringToBeReplaced);
        }
        matcher.appendTail(buffer);

        // Print the replaced matcher
        System.out.println("After Replacement: "
                           + buffer.toString());
    }
}
```

**输出：**

```java
Before Replacement: GeeksForGeeks Geeks for For Geeks Geek
After Replacement: GEEKSForGEEKS GEEKS for For GEEKS Geek
```

## 例 2

```java
// Java code to illustrate appendReplacement() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(FGF)";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "FGF FGF FGF FGF";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        System.out.println("Before Replacement: "
                           + stringToBeMatched);

        // Get the String to be replaced
        String stringToBeReplaced = "GFG";
        StringBuffer buffer = new StringBuffer();

        // Replace every matched pattern
        // with the target String
        // using appendReplacement() method
        while (matcher.find()) {
            matcher.appendReplacement(buffer,
                                      stringToBeReplaced);
        }
        matcher.appendTail(buffer);

        // Print the replaced matcher
        System.out.println("After Replacement: "
                           + buffer.toString());
    }
}
```

**输出：**

```java
Before Replacement: FGF FGF FGF FGF
After Replacement: GFG GFG GFG GFG
```

**参考：** `https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#appendReplacement-java.lang.StringBuffer-java.lang.String-`