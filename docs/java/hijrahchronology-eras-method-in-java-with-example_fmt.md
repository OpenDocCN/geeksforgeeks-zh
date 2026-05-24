# Java 中的 `HijrahChronology` `eras()` 方法示例

> 原文：[https://www.geeksforgeeks.org/hijrahchronology-eras-method-in-java-with-example/](https://www.geeksforgeeks.org/hijrahchronology-eras-method-in-java-with-example/)

`java.time.chrono.HijrahChronology` 类的 `eras()` 方法用于检索该特定 Hijrah 年表下的所有纪元。

## 语法

```java
public List eras()
```

## 参数

此方法不接受任何参数。

## 返回值

此方法返回这个特定的 Hijrah 年表下的所有时代。

以下是说明 `eras()` 方法的示例：

## 例 1

```java
// Java program to demonstrate
// eras() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // getting all HijrahEras present
            // by using eraOf() method
            List<Era> list = crono.eras();

            // display the result
            System.out.println("HijrahEra is: "
                               + (list.iterator()).next());
        }
        catch (DateTimeException e) {
            System.out.println("HijrahEra is invalid");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

## 输出

```java
HijrahEra is: AH
```

## 例 2

```java
// Java program to demonstrate
// eras() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.now(
                    Clock.systemDefaultZone());

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // getting all HijrahEras present
            // by using eraOf() method
            List<Era> list = crono.eras();

            // display the result
            System.out.println("HijrahEra is: "
                               + (list.iterator())
                                     .next());
        }
        catch (DateTimeException e) {
            System.out.println("HijrahEra is invalid");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

## 输出

```java
HijrahEra is: AH
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#eras--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#eras--)