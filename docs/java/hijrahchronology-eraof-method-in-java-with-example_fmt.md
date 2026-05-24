# Java 中的 Hijrah 年表 `eraOf()` 方法示例

> 原文：[https://www.geeksforgeeks.org/hijrahchronology-eraof-method-in-java-with-example/](https://www.geeksforgeeks.org/hijrahchronology-eraof-method-in-java-with-example/)

`java.time.chrono.HijrahChronology` 类的 `eraOf()` 方法用于通过使用数值 1 来检索 Hijrah Era，因为 `HijrahChronology` 只包含一个 `HijrahEra`。

## 语法

```java
public HijrahEra eraOf(int eraValue)
```

## 参数

该方法将 `int` 值作为将要生成 `HijrahEra` 的参数。

## 返回值

该方法使用数值 1 返回 **Hijrah 纪元**，因为 `HijrahChronology` 只包含一个 `HijrahEra`。

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
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // getting HijrahEra for the
            // given integer value
            // by using eraOf() method
            HijrahEra era = crono.eraOf(1);

            // display the result
            System.out.println("HijrahEra is: "
                               + era);
        }
        catch (DateTimeException e) {
            System.out.println("HijrahEra is invalid");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
HijrahEra is: AH
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
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // getting HijrahEra for the
            // given integer value
            // by using eraOf() method
            HijrahEra era = crono.eraOf(0);

            // display the result
            System.out.println("HijrahEra is: "
                               + era);
        }
        catch (DateTimeException e) {
            System.out.println("HijrahEra is invalid");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
HijrahEra is invalid
Exception thrown: java.time.DateTimeException: invalid Hijrah era
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#eraOf-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#eraOf-int-)