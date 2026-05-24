# Java 中的 JapaneseDate equals() 方法，示例

> 原文: [https://www.geeksforgeeks.org/japanesedate-equals-method-in-java-with-example/](https://www.geeksforgeeks.org/japanesedate-equals-method-in-java-with-example/)

`Java.time.chrono.JapaneseDate` 类的 `equals()` 方法用于将这个日本日期与另一个日本日期进行比较。

## 语法

```java
public boolean equals(Object obj)
```

## 参数
该方法以一个等价对象为参数，与该日本日期进行比较。

## 返回值
如果两个日期相等，该方法返回 `true`，否则返回 `false`。

以下是举例说明 `equals()` 方法:

## 示例 1

```java
// Java program to demonstrate
// equals() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate1
              = JapaneseDate.now();

            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate2
              = JapaneseDate.now();

            // comparing both date
            // by using equals() method
            boolean status
              = hidate1.equals(hidate2);

            // display the result
            if (status)
                System.out.println(
              "both dates are equal");
            else
                System.out.println(
              "both dates are not equal");
        }
        catch (DateTimeException e) {
            System.out.println(
              "passed parameter can"
              + " not form a date");
            System.out.println(
              "Exception thrown: " + e);
        }
    }
}
```

**输出**

```java
both dates are equal
```

## 示例 2

```java
// Java program to demonstrate
// equals() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate1
              = JapaneseDate.now();

            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate2
              = JapaneseDate.of(2008, 03, 23);

            // comparing both date
            // by using equals() method
            boolean status
              = hidate1.equals(hidate2);

            // display the result
            if (status)
                System.out.println(
              "both dates are equal");
            else
                System.out.println(
              "both dates are not equal");
        }
        catch (DateTimeException e) {
            System.out.println(
              "passed parameter can"
              + " not form a date");
            System.out.println(
              "Exception thrown: " + e);
        }
    }
}
```

**输出**

```java
both dates are not equal
```

**参考:** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#equals-java.lang.Object-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#equals-java.lang.Object-)