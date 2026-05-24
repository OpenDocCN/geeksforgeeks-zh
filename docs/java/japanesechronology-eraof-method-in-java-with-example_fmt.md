# Java 中的 JapaneseChronology eraOf() 方法示例

> 原文：[https://www.geeksforgeeks.org/japanesechronology-eraof-method-in-java-with-example/](https://www.geeksforgeeks.org/japanesechronology-eraof-method-in-java-with-example/)

`java.time.chrono.JapaneseChronology` 类的 `eraOf()` 方法用于通过使用数值来检索 `JapaneseEra`。

## 语法

```java
public JapaneseEra eraOf(int eraValue)
```

## 参数

该方法将 `int` 类型的值 `eraValue` 作为参数，用于生成对应的日本时代（`JapaneseEra`）。

## 返回值

该方法使用给定的数值返回对应的 `JapaneseEra`。

以下是举例说明 `eraOf()` 方法的例子：

## 示例 1

```java
// Java program to demonstrate
// eraOf() method

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
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in LocalDate
            JapaneseChronology crono
                = hidate.getChronology();

            // getting JapaneseEra for the
            // given integer value
            // by using eraOf() method
            JapaneseEra era = crono.eraOf(0);

            // display the result
            System.out.println(
                "JapaneseEra is: "
                + era);
        }
        catch (DateTimeException e) {
            System.out.println(
                "JapaneseEra is invalid");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
JapaneseEra is: Taisho
```

## 示例 2

```java
// Java program to demonstrate
// eraOf() method

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
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in LocalDate
            JapaneseChronology crono
                = hidate.getChronology();

            // getting JapaneseEra for the
            // given integer value
            // by using eraOf() method
            JapaneseEra era = crono.eraOf(2);

            // display the result
            System.out.println("JapaneseEra is: "
                               + era);
        }
        catch (DateTimeException e) {
            System.out.println(
                "JapaneseEra is invalid");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
JapaneseEra is: Heisei
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#eraOf-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#eraOf-int-)