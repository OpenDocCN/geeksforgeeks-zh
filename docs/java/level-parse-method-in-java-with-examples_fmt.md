# Java 中的 Level parse()方法示例

> 原文：[https://www.geeksforgeeks.org/level-parse-method-in-java-with-examples/](https://www.geeksforgeeks.org/level-parse-method-in-java-with-examples/)

`java.util.logging.Level` 的 `parse()` 方法用于将级别名称字符串解析为级别。日志记录级别的名称必须是有效的日志记录名称。参数字符串可以由级别名称或整数值组成。级别示例名称：`"INFO"`、`"800"`。

## 语法

```java
public static Level parse(String name)
    throws IllegalArgumentException
```

## 参数

该方法接受一个 `name`，该 `name` 是要解析的字符串。

## 返回

该方法返回解析后的值。

## 异常

该方法抛出如下异常：

*   `NullPointerException`：如果名称为 `null`。
*   `IllegalArgumentException`：如果值无效。有效值是介于 `Integer.MIN_VALUE` 和 `Integer.MAX_VALUE` 之间的整数，以及所有已知的级别名称。

下面的程序说明 `parse()` 方法：

### 程序 1

```java
// Java program to illustrate parse() method

import java.util.logging.Level;

public class GFG {

    public static void main(String[] args)
    {

        // Get level of logger using
        // parse method.
        Level level
            = Level.parse("WARNING");

        // print result
        System.out.println("Level  = "
                           + level.toString());
    }
}
```

**Output:**

```java
Level  = WARNING
```

### 程序 2

```java
// Java program to illustrate parse() method

import java.util.logging.Level;

public class GFG {

    public static void main(String[] args)
    {

        // Get level of logger using
        // parse method.
        Level level
            = Level.parse("400");

        // print result
        System.out.println("Level  = "
                           + level.toString());
    }
}
```

**Output:**

```java
Level  = FINER
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/util/logging/Level.html#parse(java.lang.Object)](https://docs.oracle.com/javase/10/docs/api/java/util/logging/Level.html#parse(java.lang.Object))