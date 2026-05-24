# Java 中的 MinguoDate.getChronology() 方法示例

> 原文：[https://www.geeksforgeeks.org/minguodate-getchronology-method-in-java-with-example/](https://www.geeksforgeeks.org/minguodate-getchronology-method-in-java-with-example/)

`java.time.chrono.MinguoDate` 类的 `getChronology()` 方法用于检索该日期所属的民国日期年代学。

## 语法

```java
public MinguoChronology getChronology()
```

## 参数
此方法不接受任何参数。

## 返回值
此方法返回此民国日期的年代学。

以下是 `getChronology()` 方法的示例：

### 示例 1

```java
// Java program to demonstrate
// getChronology() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // getting chronology of this date
            // by using getChronology() method
            MinguoChronology crono
                = hidate.getChronology();

            // display the result
            System.out.println("MinguoChronology: "
                               + crono);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
MinguoChronology: Minguo
```

### 示例 2

```java
// Java program to demonstrate
// getChronology() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.of(2008, 04, 24);

            // getting chronology of this date
            // by using getChronology() method
            MinguoChronology crono
                = hidate.getChronology();

            // display the result
            System.out.println("MinguoChronology: "
                               + crono);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
MinguoChronology: Minguo
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#getChronology--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#getChronology--)