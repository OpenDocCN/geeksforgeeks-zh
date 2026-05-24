# 检查 Java 中字符串是否只包含空格的程序

> 原文：[https://www.geeksforgeeks.org/program-to-check-if-a-string-in-java-contains-only-whitespaces/](https://www.geeksforgeeks.org/program-to-check-if-a-string-in-java-contains-only-whitespaces/)

给定一个字符串，任务是在 Java 中检查这个字符串是否只包含空格或一些文本。

**示例：**

```
Input: str = "              " 
Output: True

Input: str = "GFG"
Output: False
```

**方法：**

*   获取要在字符串中检查的字符串。
*   我们可以使用 [`String`](https://www.geeksforgeeks.org/string-class-in-java/) 类的 [`trim()`](https://www.geeksforgeeks.org/java-string-trim-method-example/) 方法来移除字符串中的前导空格。
    **语法：**

    ```
    str.trim()
    ```

*   然后我们可以使用 [`String`](https://www.geeksforgeeks.org/string-class-in-java/) 类的 [`isEmpty()`](https://www.geeksforgeeks.org/java-string-isempty-method-example/) 方法来检查结果字符串是否为空。如果字符串只包含空格，那么这个方法将返回 `true`。
    **语法：**

    ```
    str.isEmpty()
    ```

*   使用[方法链接](https://www.geeksforgeeks.org/method-chaining-in-java-with-examples/)将两种方法结合使用。

    ```
    str.trim().isEmpty();
    ```

*   如果上述条件为 `true` 则打印 `true`，否则打印 `false`。

下面是上述方法的实现：

```java
// Java Program to check if
// the String is not all whitespaces

class GFG {

    // Function to check if the String is all whitespaces
    public static boolean isStringAllWhiteSpace(String str)
    {
        // Remove the leading whitespaces using trim()
        // and then check if this string is empty
        if (str.trim().isEmpty())
            return true;
        else
            return false;
    }

    // Driver code
    public static void main(String[] args)
    {
        String str1 = "GeeksforGeeks";
        String str2 = "              ";

        System.out.println("Is string [" + str1
                           + "] only whitespaces? "
                           + isStringAllWhiteSpace(str1));
        System.out.println("Is string [" + str2
                           + "] only whitespaces? "
                           + isStringAllWhiteSpace(str2));
    }
}
```

**输出：**

```
Is string [GeeksforGeeks] only whitespaces? false
Is string [              ] only whitespaces? true
```