# 检查一个字符串是否以 Java 中任何给定的前缀开头

> 原文: [https://www.geeksforgeeks.org/check-if-a-string-starts-with-any-of-the-given-prefixes-in-java/](https://www.geeksforgeeks.org/check-if-a-string-starts-with-any-of-the-given-prefixes-in-java/)

给定一个字符串和前缀数组。任务是检查给定的字符串是否以任何给定的前缀开头。

**示例:**

> **输入**: String = "Geeksforgeeks", 前缀 = { "Geeks", "for", "Gfor" }
> **输出**: true
>
> **输入**: String = "geeksforgeeks", 前缀 = { "Freaks", "for", "Freak" }
> **输出**: false

以下是可用于完成给定任务的方法:

## 1. 朴素方法

此方法涉及显式地检查字符串是否以每个前缀数组元素开头。

**算法:**

1.  获取要匹配的字符串和前缀。
2.  使用循环，遍历前缀并检查字符串是否以各自的前缀开头。这是在 `String.startsWith()` 方法的帮助下完成的。
3.  如果匹配任何前缀，则返回 `true`，否则返回 `false`。

**程序 1:**

```java
class PrefixSearch {
    public static void main(String[] args)
    {
        // Array of prefixes
        String[] arr = { "Geeks", "for", "Gfor" };

        // Given string
        String str = "GeeksforGeeks";

        boolean result = false;

        // Check for each prefix element
        for (int i = 0; i < 3; i++) {
            if (str.startsWith(arr[i])) {
                result = true;
                break;
            }
        }

        if (result)
            System.out.println("Given String "
                               + "starts with one of the prefixes.");
        else
            System.out.println("Given String do not "
                               + "starts with one of the prefixes.");
    }
}
```

**输出:**

```java
Given String starts with one of the prefixes.
```

**程序 2:**

```java
class PrefixSearch {
    public static void main(String[] args)
    {
        // Array of prefixes
        String[] arr = { "Freaks", "for", "Freak" };

        // Given string
        String str = "GeeksforGeeks";

        boolean result = false;

        // Check for each prefix element
        for (int i = 0; i < 3; i++) {
            if (str.startsWith(arr[i])) {
                result = true;
                break;
            }
        }

        if (result)
            System.out.println("Given String "
                               + "starts with one of the prefixes.");
        else
            System.out.println("Given String do not "
                               + "starts with one of the prefixes.");
    }
}
```

**输出:**

```java
Given String do not starts with one of the prefixes.
```

## 2. 使用正则表达式

**算法:**

1.  获取要匹配的字符串和前缀。
2.  形成一个正则表达式来检查字符串是否以任何前缀开头。这可以使用 `String.matches()` 方法来完成。
3.  如果匹配任何前缀，则返回 `true`，否则返回 `false`。

**程序 1:**

```java
class PrefixSearch {
    public static void main(String[] args)
    {
        // Array of prefixes
        String[] arr = { "Geeks", "for", "Gfor" };

        // Given String
        String str = "GeeksforGeeks";

        // Check for prefixes using Regex
        if (str.matches("(" + arr[0] + "|"
                        + arr[1] + "|"
                        + arr[2] + ").*"))
            System.out.println("Given String "
                               + "starts with one of the prefixes.");
        else
            System.out.println("Given String do not "
                               + "starts with one of the prefixes.");
    }
}
```

**输出:**

```java
Given String starts with one of the prefixes.
```

**程序 2:**

```java
class PrefixSearch {
    public static void main(String[] args)
    {
        // Array of prefixes
        String[] arr = { "Freaks", "for", "Freak" };

        // Given String
        String str = "GeeksforGeeks";

        // Check for prefixes using Regex
        if (str.matches("(" + arr[0] + "|"
                        + arr[1] + "|"
                        + arr[2] + ").*"))
            System.out.println("Given String "
                               + "starts with one of the prefixes.");
        else
            System.out.println("Given String do not "
                               + "starts with one of the prefixes.");
    }
}
```

**输出:**

```java
Given String do not starts with one of the prefixes.
```

## 3. 使用 Java 8 Streams API

**算法:**

1.  获取要匹配的字符串和前缀。
2.  使用 `Stream.of()`
3.  将前缀转换为 `Stream<String>`，使用谓词 `String::startsWith` 检查是否有任何前缀匹配。这是使用 `Stream.anyMatch()` 方法完成的。
4.  如果有匹配的前缀，则返回 `true`，否则返回 `false`。

**程序 1:**

```java
import java.util.stream.Stream;

class PrefixSearch {
    public static void main(String[] args)
    {
        // Array of prefixes
        String[] arr = { "Geeks", "for", "Gfor" };

        // Given String
        String str = "GeeksforGeeks";

        // Convert the Prefixes into Stream using Stream.of()
        // and check if any prefix matches using Predicate
        // str::startsWith
        if (Stream.of(arr)
                .anyMatch(str::startsWith))
            System.out.println("Given String "
                               + "starts with one of the prefixes.");
        else
            System.out.println("Given String do not "
                               + "starts with one of the prefixes.");
    }
}
```

**输出:**

```java
Given String starts with one of the prefixes.
```

**程序 2:**

```java
import java.util.stream.Stream;

class PrefixSearch {
    public static void main(String[] args)
    {
        // Array of prefixes
        String[] arr = { "Freaks", "for", "Freak" };

        // Given String
        String str = "GeeksforGeeks";

        // Convert the Prefixes into Stream using Stream.of()
        // and check if any prefix matches using Predicate
        // str::startsWith
        if (Stream.of(arr)
                .anyMatch(str::startsWith))
            System.out.println("Given String "
                               + "starts with one of the prefixes.");
        else
            System.out.println("Given String do not "
                               + "starts with one of the prefixes.");
    }
}
```

**输出:**

```java
Given String do not starts with one of the prefixes.
```