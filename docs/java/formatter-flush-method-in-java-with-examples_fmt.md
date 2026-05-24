# Java 中的 Formatter flush() 方法示例

> 原文：[https://www.geeksforgeeks.org/formatter-flush-method-in-java-with-examples/](https://www.geeksforgeeks.org/formatter-flush-method-in-java-with-examples/)

## flush() 方法介绍

`flush()` 方法是 `java.util.Formatter` 的内置方法，用于刷新格式化程序。将目标中的任何缓冲输出写入底层操作系统称为刷新。

## 语法

```java
public void flush()
```

## 参数

该功能不接受参数。

## 返回值

函数不返回任何东西，只是刷新格式化程序。因此返回类型是 `void`。

## 错误和异常

关闭格式化程序后使用该函数时，该函数抛出 `FormatterClosedException`。

## 程序 1

下面是上述功能的实现：

```java
// Java program to implement
// the above function

import java.util.Formatter;
import java.util.Locale;

public class Main {

    public static void main(String[] args)
    {
        // Get the string Buffer
        StringBuffer buffer = new StringBuffer();

        // Object creation
        Formatter frmt
            = new Formatter(buffer,
                            Locale.CANADA);

        // Format a new string
        String name = "My name is Gopal Dave";
        frmt.format("What is your name? \n%s !",
                    name);

        // Print the Formatted string
        System.out.println(frmt);

        // flushes the formatter
        frmt.flush();
        System.out.println("Flushed");
    }
}
```

## 输出

```java
What is your name? 
My name is Gopal Dave !
Flushed
```

## 程序 2

```java
// Java program to implement
// the above function

import java.util.Formatter;
import java.util.Locale;

public class Main {

    public static void main(String[] args)
    {
        try {
            // Get the string Buffer
            StringBuffer buffer
                = new StringBuffer();

            // Object creation
            Formatter frmt
                = new Formatter(buffer,
                                Locale.CANADA);

            // Format a new string
            String name = "My name is Gopal Dave";
            frmt.format("What is your name? \n%s !",
                        name);

            // Print the Formatted string
            System.out.println(frmt);

            // closes the formatter
            frmt.close();

            // close the frmt
            frmt.flush();
            System.out.println("Flushed");
        }
        catch (Exception e) {
            System.out.println("\nException is: "
                               + e);
        }
    }
}
```

## 输出

```java
What is your name? 
My name is Gopal Dave !

Exception is: java.util.FormatterClosedException
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/util/Formatter.html#close()](https://docs.oracle.com/javase/10/docs/api/java/util/Formatter.html#close())