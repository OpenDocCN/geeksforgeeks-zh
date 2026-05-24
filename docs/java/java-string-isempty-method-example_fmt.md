# Java String isEmpty()方法，带示例

> 原文: [https://www.geeksforgeeks.org/java-string-isempty-method-example/](https://www.geeksforgeeks.org/java-string-isempty-method-example/)

## 方法介绍

`Java.lang.String.isEmpty()`方法用于检查字符串是否为空。如果给定的字符串为空，此方法返回 `true`，否则返回 `false`。自 JDK 1.6 起，`String`类的`isEmpty()`方法就被包含在 Java 字符串类中。换句话说，如果字符串的长度为 0，则此方法返回 `true`。

**示例：**

```java
Input String1 : Hello_Gfg
Input String2 :
Output for String1 : false
Output for String2 : true
```

## 语法

```java
public boolean isEmpty()
```

返回值：如果字符串的长度为 0，则返回 `true`。

## 示例代码

```java
// Java program to demonstrate working of
// isEmpty() method
class Gfg {
    public static void main(String args[])
    {
        // non-empty string
        String str1 = "Hello_Gfg";

        // empty string
        String str2 = "";

        // prints false
        System.out.println(str1.isEmpty());

        // prints true
        System.out.println(str2.isEmpty());
    }
}
```

## 输出

```java
false
true
```