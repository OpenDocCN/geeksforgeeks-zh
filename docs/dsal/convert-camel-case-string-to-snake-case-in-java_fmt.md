# 在 Java 中将驼峰式字符串转换为蛇形式

> 原文：[https://www.geeksforgeeks.org/convert-camel-case-string-to-snake-case-in-java/](https://www.geeksforgeeks.org/convert-camel-case-string-to-snake-case-in-java/)

给定*驼峰式*中的一个字符串，任务是编写一个 Java 程序，将给定的字符串从*驼峰式*转换为*蛇形式*并打印修改后的字符串。

**示例：**

> **输入：** GeeksForGeeks
>
> **输出：** geeks_for_geeks
>
> **输入：** CamelCaseToSnakeCase
>
> **输出：** camel_case_to_snake_case

**方法 1：朴素方法**

*   首先，我们用一个空字符串初始化一个变量`result`，并将第一个字符（小写）附加到它上面。
*   现在，从第一个索引到最后一个索引迭代字符串的每个字符，如果字符是大写字母，我们将`"_"`和字符（小写）追加到结果中，否则只追加字符。

下面是上述方法的实现：

## Java 实现

```java
class GFG {

    // Function to convert camel case
    // string to snake case string
    public static String camelToSnake(String str)
    {

        // Empty String
        String result = "";

        // Append first character(in lower case)
        // to result string
        char c = str.charAt(0);
        result = result + Character.toLowerCase(c);

        // Traverse the string from
        // 1st index to last index
        for (int i = 1; i < str.length(); i++) {

            char ch = str.charAt(i);

            // Check if the character is upper case
            // then append '_' and such character
            // (in lower case) to result string
            if (Character.isUpperCase(ch)) {
                result = result + '_';
                result
                    = result
                      + Character.toLowerCase(ch);
            }

            // If the character is lower case then
            // add such character into result string
            else {
                result = result + ch;
            }
        }

        // return the result
        return result;
    }

    public static void main(String args[])
    {
        // Given string str
        String str = "GeeksForGeeks";

        // Print the modified string
        System.out.print(camelToSnake(str));
    }
}
```

**Output：**

```
geeks_for_geeks
```

**方法二：使用 `String.replaceAll`**

*   想法是使用 [`String.replaceAll`](https://www.geeksforgeeks.org/java-lang-string-replace-method-java/) 方法将给定的字符串从*驼峰式*转换为*蛇形式*。
*   该方法接受两个参数：一个正则表达式和一个替换字符串。它用替换字符串替换正则表达式匹配的部分，并打印修改后的字符串。

下面是上述方法的实现：

## Java 实现

```java
class GFG {

    // Function to convert camel case
    // string to snake case string
    public static String
    camelToSnake(String str)
    {
        // Regular Expression
        String regex = "([a-z])([A-Z]+)";

        // Replacement string
        String replacement = "$1_$2";

        // Replace the given regex
        // with replacement string
        // and convert it to lower case.
        str = str
                  .replaceAll(
                      regex, replacement)
                  .toLowerCase();

        // return string
        return str;
    }

    // Driver Code
    public static void main(String args[])
    {
        // Given string str
        String str = "GeeksForGeeks";

        // Print the modified string
        System.out.print(camelToSnake(str));
    }
}
```

**Output：**

```
geeks_for_geeks
```