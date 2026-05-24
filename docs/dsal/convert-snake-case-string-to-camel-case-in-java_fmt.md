# 将 Java 中的蛇形字符串转换为驼峰格式

> 原文：[https://www.geeksforgeeks.org/convert-snake-case-string-to-camel-case-in-java/](https://www.geeksforgeeks.org/convert-snake-case-string-to-camel-case-in-java/)

在*蛇形格式*中给定一个字符串，任务是编写一个 [`Java`](https://www.geeksforgeeks.org/java/) 程序，将给定的字符串从*蛇形格式*转换为*驼峰格式*并打印修改后的字符串。

**示例：**

> **输入：** `str = "geeks_for_geeks"`
> **输出：** `GeeksForGeeks`
>
> **输入：** `str = "snake_case_to_camel_case"`
> **输出：** `SnakeCaseToCamelCase`

## 方法 1：使用遍历

1.  想法是首先将字符串的第一个字母大写。
2.  然后将字符串转换为 `StringBuilder`。
3.  然后逐个字符地从第一个索引遍历到最后一个索引，并检查该字符是否带下划线 `_`，然后删除该字符并大写下划线的下一个字符。
4.  打印修改后的字符串。

下面是上述方法的实现：

```java
// Java program for the above approach

import java.io.*;

class GFG {

    // Function to convert snake case
    // to camel case
    public static String snakeToCamel(String str)
    {
        // Capitalize first letter of string
        str = str.substring(0, 1).toUpperCase()
              + str.substring(1);

        // Convert to StringBuilder
        StringBuilder builder = new StringBuilder(str);

        // Traverse the string character by
        // character and remove underscore
        // and capitalize next letter
        for (int i = 0; i < builder.length(); i++) {

            // Check char is underscore
            if (builder.charAt(i) == '_') {

                builder.deleteCharAt(i);
                builder.replace(
                    i, i + 1,
                    String.valueOf(
                        Character.toUpperCase(
                            builder.charAt(i))));
            }
        }

        // Return in String type
        return builder.toString();
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Given String
        String str = "geeks_for_geeks";

        // Function Call
        str = snakeToCamel(str);

        // Modified String
        System.out.println(str);
    }
}
```

**输出：**

```
GeeksForGeeks
```

## 方法 2：使用 `String.replaceFirst()` 方法

1.  其思想是使用 [`String.replaceFirst()`](https://www.geeksforgeeks.org/java-lang-string-replace-method-java/) 方法将给定的字符串从蛇形格式转换为驼峰格式。
2.  首先，将字符串的第一个字母大写。
3.  运行一个循环，直到字符串包含下划线 `_`。
4.  将下划线后出现的第一个字母替换为下划线下一个字母的大写形式。
5.  打印修改后的字符串。

下面是上述方法的实现：

```java
// Java program for the above approach

class GFG {

    // Function to convert the string
    // from snake case to camel case
    public static String snakeToCamel(String str)
    {
        // Capitalize first letter of string
        str = str.substring(0, 1).toUpperCase()
              + str.substring(1);

        // Run a loop till string
        // string contains underscore
        while (str.contains("_")) {

            // Replace the first occurrence
            // of letter that present after
            // the underscore, to capitalize
            // form of next letter of underscore
            str = str.replaceFirst(
                      "_[a-z]",
                      String.valueOf(
                          Character.toUpperCase(
                              str.charAt(
                                  str.indexOf("_") + 1))));
        }

        // Return string
        return str;
    }

    // Driver Code
    public static void main(String args[])
    {
        // Given string
        String str = "geeks_for_geeks";

        // Print the modified string
        System.out.print(snakeToCamel(str));
    }
}
```

**输出：**

```
GeeksForGeeks
```