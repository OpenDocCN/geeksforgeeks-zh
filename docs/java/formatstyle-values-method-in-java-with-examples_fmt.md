# Java 中的 FormatStyle values() 方法示例

> 原文：[https://www.geeksforgeeks.org/formatstyle-values-method-in-java-with-examples/](https://www.geeksforgeeks.org/formatstyle-values-method-in-java-with-examples/)

`FormatStyle` 枚举的 `values()` 方法用于获取包含该 `FormatStyle` 所有单位的数组，按照它们被声明的顺序。

## 语法

```java
public static FormatStyle[] values()
```

## 参数
此方法不接受任何参数。

## 返回值
此方法返回一个包含此枚举类型常量的数组，按照它们被声明的顺序。

下面的程序说明了 `FormatStyle.values()` 方法：

## 程序 1

```java
// Java program to demonstrate
// FormatStyle.values() method

import java.time.format.FormatStyle;

public class GFG {
    public static void main(String[] args)
    {

        // Get FormatStyle instance
        FormatStyle formatStyle
            = FormatStyle.valueOf("FULL");

        // Get the constants using values()
        FormatStyle[] array
            = formatStyle.values();

        // Print the values
        for (int i = 0; i < array.length; i++)
            System.out.println(array[i]);
    }
}
```

**输出：**

```java
FULL
LONG
MEDIUM
SHORT
```

## 程序 2

```java
// Java program to demonstrate
// FormatStyle.values() method

import java.time.format.FormatStyle;

public class GFG {
    public static void main(String[] args)
    {

        // Get FormatStyle instance
        FormatStyle formatStyle
            = FormatStyle.valueOf("FULL");

        // Get the constants using values()
        FormatStyle[] array
            = formatStyle.values();

        // Print the values
        System.out.println("FormatStyle length: "
                           + array.length);
    }
}
```

**输出：**

```java
FormatStyle length: 4
```

参考文献：[https://docs.oracle.com/javase/10/docs/api/java/time/format/FormatStyle.html](https://docs.oracle.com/javase/10/docs/api/java/time/format/FormatStyle.html)