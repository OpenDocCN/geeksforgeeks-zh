# Java中的HijrahChronology.getId()方法示例

> 原文：[https://www.geeksforgeeks.org/hijrahchronology-getid-method-in-java-with-example/](https://www.geeksforgeeks.org/hijrahchronology-getid-method-in-java-with-example/)

`HijrahChronology`类的`getId()`方法用于检索该特定年表的标识符。

## 语法

```java
public String getId()
```

## 参数

此方法不接受任何参数。

## 返回值

该方法返回该特定年表的标识符。

以下是说明`getId()`方法的例子：

## 例1

```java
// Java program to demonstrate
// getId() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing
        // HijrahDate Object
        HijrahDate hidate = HijrahDate.now();

        // getting HijrahChronology
        // used in HijrahDate
        HijrahChronology crono
            = hidate.getChronology();

        // getting id of this Chronology
        // by using getId() method
        String id = crono.getId();

        // display the result
        System.out.println("id : " + id);
    }
}
```

## 输出

```java
id : Hijrah-umalqura
```

## 例2

```java
// Java program to demonstrate
// getId() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing
        // HijrahDate Object
        HijrahDate hidate
            = HijrahDate.now(
                Clock.systemDefaultZone());

        // getting HijrahChronology
        // used in HijrahDate
        HijrahChronology crono
            = hidate.getChronology();

        // getting id of this Chronology
        // by using getId() method
        String id = crono.getId();

        // display the result
        System.out.println("id : " + id);
    }
}
```

## 输出

```java
id : Hijrah-umalqura
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#getId--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#getId--)