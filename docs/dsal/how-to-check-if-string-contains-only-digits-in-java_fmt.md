# 如何在 Java 中检查字符串是否只包含数字

> 原文: [https://www.geeksforgeeks.org/how-to-check-if-string-contains-only-digits-in-java/](https://www.geeksforgeeks.org/how-to-check-if-string-contains-only-digits-in-java/)

给定一个字符串 `str`，任务是编写一个 [Java](https://www.geeksforgeeks.org/java/) 程序来检查一个字符串是否只包含数字。如果是，那么打印真，否则打印假。

**例:**

> **输入:** `str = "1234"`
> **输出:** 真
> **解释:**
> 给定字符串只包含数字，因此输出为真。
>
> **输入:** `str = " geeksforgeeck 2020 "`
> **输出:** 假
> **说明:**
> 给定字符串包含字母字符和数字，因此输出为假。

## 1. 使用遍历 (Using Traversal)

思路是遍历字符串中的每个字符，并检查字符串的字符是否只包含从 `0` 到 `9` 的数字。如果字符串的所有字符都只包含数字，则返回 `true`，否则返回 `false`。

下面是上述方法的实现:

```java
// Java program for the above approach
// contains only digits
class GFG {

    // Function to check if a string
    // contains only digits
    public static boolean onlyDigits(String str, int n) {
        // Traverse the string from
        // start to end
        for (int i = 0; i < n; i++) {
            // Check if character is
            // digit from 0-9
            // then return true
            // else false
            if (str.charAt(i) >= '0' && str.charAt(i) <= '9') {
                return true;
            } else {
                return false;
            }
        }
        return false;
    }

    // Driver Code
    public static void main(String args[]) {
        // Given string str
        String str = "1234";
        int len = str.length();

        // Function Call
        System.out.println(onlyDigits(str, len));
    }
}
```

**Output:**

```
true
```

**时间复杂度:** `O(N)`，其中 `N` 为给定字符串的长度。
**辅助空间:** `O(1)`

## 2. 使用 Character.isDigit(char ch)

思路是遍历字符串的每个字符，并使用 [`Character.isDigit(char ch)`](https://www.geeksforgeeks.org/character-isdigit-method-in-java-with-examples/) 检查指定字符是否为数字。如果字符是数字则返回 `true`，否则返回 `false`。

下面是上述方法的实现:

```java
// Java program to check if a string
// contains only digits
class GFG {

    // Function to check if a string
    // contains only digits
    public static boolean onlyDigits(String str, int n) {
        // Traverse the string from
        // start to end
        for (int i = 0; i < n; i++) {
            // Check if the sepecified
            // character is a digit then
            // return true,
            // else return false
            if (Character.isDigit(str.charAt(i))) {
                return true;
            } else {
                return false;
            }
        }
        return false;
    }

    // Driver Code
    public static void main(String args[]) {
        // Given string str
        String str = "1234";
        int len = str.length();

        // Function Call
        System.out.println(onlyDigits(str, len));
    }
}
```

**Output:**

```
true
```

**时间复杂度:** `O(N)`，其中 `N` 为给定字符串的长度。
**辅助空间:** `O(1)`

## 3. 使用正则表达式 (Using Regular Expression)

1.  获取字符串。
2.  创建一个[正则表达式](https://www.geeksforgeeks.org/write-regular-expressions/)来检查字符串是否只包含数字，如下所述:

    ```java
    regex = "[0-9]+";
    ```

3.  用正则表达式匹配给定的字符串。在 Java 中，这可以通过使用 [`Pattern.matcher()`](https://www.geeksforgeeks.org/matcher-pattern-method-in-java-with-examples/) 来完成。
4.  如果字符串与给定的正则表达式匹配，则返回 `true`，否则返回 `false`。

下面是上述方法的实现:

```java
// Java program to check if a string
// contains only digits
import java.util.regex.*;
class GFG {

    // Function to validate URL
    // using regular expression
    public static boolean onlyDigits(String str) {
        // Regex to check string
        // contains only digits
        String regex = "[0-9]+";

        // Compile the ReGex
        Pattern p = Pattern.compile(regex);

        // If the string is empty
        // return false
        if (str == null) {
            return false;
        }

        // Find match between given string
        // and regular expression
        // using Pattern.matcher()
        Matcher m = p.matcher(str);

        // Return if the string
        // matched the ReGex
        return m.matches();
    }

    // Driver Code
    public static void main(String args[]) {
        // Given string str
        String str = "1234";

        // Function Call
        System.out.println(onlyDigits(str));
    }
}
```

**Output:**

```
true
```

**时间复杂度:** `O(N)`，其中 `N` 为给定字符串的长度。
**辅助空间:** `O(1)`