# 将字符串转换为布尔值的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-convert-a-string-to-boolean/](https://www.geeksforgeeks.org/java-program-to-convert-a-string-to-boolean/)

给定字符串 `str`，任务是编写一个 Java 程序，将给定字符串转换为其布尔值。

**示例：**

```java
Input: str = "true"
Output: true
Explanation: The boolean equivalent of true is true itself.

Input: str = "false"
Output: false
Explanation: The boolean equivalent of false is false itself.

Input: str = "yes"
Output: false
Explanation: The boolean equivalent of yes is false since the given value is not equal to true.
```

**字符串**——Java 中的字符串是由一个字符数组在内部支持的对象。由于数组是不可变的，而字符串也是一种保存字符的特殊数组，因此字符串也是不可变的。

**布尔**——布尔数据类型仅由两个值组成——`true` 和 `false`。如果字符串为 `true`（忽略大小写），则布尔等价为 `true`，否则为 `false`。

## 方法

在 Java 中，有许多方法可以将给定的字符串转换为布尔值。下面列出了其中的一些。

*   使用 `Boolean.parseBoolean()` 方法
*   使用 `Boolean.valueOf()` 方法

### 1. 使用 `Boolean.parseBoolean()` 方法

*   使用 [`Boolean.parseBoolean()`](https://www.geeksforgeeks.org/boolean-parseboolean-method-in-java-with-examples/) 方法。这是将字符串转换为布尔值的最常见方法。
*   此方法用于将给定字符串转换为其原始布尔值。
*   如果给定的字符串包含值 `true`（忽略大小写），则该方法返回 `true`。如果字符串包含除 `true` 以外的任何其他值，则该方法返回 `false`。

**语法：**

```java
boolean boolValue = Boolean.parseBoolean(String str);
```

以下是上述方法的实现：

## Java 代码

```java
// Java Program to Convert a String to Boolean

class GFG {

    // Function to convert a string
    // to its boolean value
    public static boolean
    stringToBoolean(String str)
    {
        // convert a given string to
        // its primitive boolean value
        // using parseBoolean() method
        boolean b1
            = Boolean.parseBoolean(str);

        // returns primitive boolean value
        return b1;
    }

    // Driver code
    public static void main(String args[])
    {
        // Given String str
        String str = "yes";

        // print the result
        System.out.println(
            stringToBoolean(str));

        // Given String str
        str = "true";

        // print the result
        System.out.println(
            stringToBoolean(str));

        // Given String str
        str = "false";

        // print the result
        System.out.println(
            stringToBoolean(str));
    }
}
```

**输出**

```java
false
true
false
```

### 2. 使用 `Boolean.valueOf()` 方法

它类似于 [`Boolean.parseBoolean()`](https://www.geeksforgeeks.org/boolean-parseboolean-method-in-java-with-examples/) 方法，但它返回的是一个布尔对象，而不是一个原始布尔值。

**语法：**

```java
boolean boolValue = Boolean.valueOf(String str);
```

以下是上述方法的实现：

## Java 代码

```java
// Java Program to Convert a String to Boolean

class GFG {

    // Function to convert a string
    // to its boolean object
    public static boolean
    stringToBoolean(String str)
    {
        // convert a given string to
        // its boolean object using
        // valueOf() method
        boolean b1 = Boolean.valueOf(str);

        // returns boolean object
        return b1;
    }

    // Driver code
    public static void main(String args[])
    {
        // Given String str
        String str = "yes";

        // print the result
        System.out.println(
            stringToBoolean(str));

        // Given String str
        str = "true";

        // print the result
        System.out.println(
            stringToBoolean(str));

        // Given String str
        str = "false";

        // print the result
        System.out.println(
            stringToBoolean(str));
    }
}
```

**输出**

```java
false
true
false
```