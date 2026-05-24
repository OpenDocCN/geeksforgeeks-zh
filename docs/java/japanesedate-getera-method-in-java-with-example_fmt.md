# Java 中的 JapaneseDate getEra() 方法示例

> 原文: [https://www.geeksforgeeks.org/japanesedate-getera-method-in-java-with-example/](https://www.geeksforgeeks.org/japanesedate-getera-method-in-java-with-example/)

`Java.time.chrono.JapaneseDate` 类的 `getEra()` 方法用于检索与该日本日期相关的纪元。

## 语法

```java
public JapaneseEra getEra()
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法返回这个日本日期的时代。

以下是举例说明 `getEra()` 方法:

### 示例 1

```java
// Java program to demonstrate
// getEra() method

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
            JapaneseDate hidate = JapaneseDate.now();

            // getting chronology of this date
            // by using getChronology() method
            JapaneseEra crono = hidate.getEra();

            // display the result
            System.out.println("JapaneseEra: "
                               + crono);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**输出**

```java
JapaneseEra: Heisei
```

### 示例 2

```java
// Java program to demonstrate
// getEra() method

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
                = JapaneseDate.of(2008, 04, 24);

            // getting chronology of this date
            // by using getChronology() method
            JapaneseEra crono = hidate.getEra();

            // display the result
            System.out.println("JapaneseEra: "
                               + crono);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**输出**

```java
JapaneseEra: Heisei
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#getEra--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#getEra--)