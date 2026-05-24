# Java 中的 Minguo 年表 `eras()` 方法示例

> 原文：`https://www.geeksforgeeks.org/minguochronology-eras-method-in-java-with-example/`

`Java.time.chrono.MinguoChronology` 类的 `eras()` 方法用于检索该特定 Minguo 年表下的所有纪元。

**语法：**

```java
public List eras()
```

**参数：** 此方法不接受任何参数。

**返回值：** 此方法返回这个特定的 Minguo 年表下的所有时代。

以下是说明 `eras()` 方法的示例：

**例 1：**

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
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // getting all MinguoEras present
            // by using eraOf() method
            List<Era> list = crono.eras();

            // display the result
            System.out.println(
                "MinguoEra is: "
                + (list.iterator()).next());
        }
        catch (DateTimeException e) {
            System.out.println(
                "MinguoEra is invalid");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出：**

```
MinguoEra is: BEFORE_ROC
```

**例 2：**

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
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // getting all MinguoEras present
            // by using eraOf() method
            List<Era> list = crono.eras();

            // getting list Iterator
            Iterator iter = list.iterator();

            // display the result
            System.out.println("List of MinguoEra : ");
            for (int i = 0; i < 2; i++)
                System.out.println(iter.next());
        }
        catch (DateTimeException e) {
            System.out.println(
                "MinguoEra is invalid");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出：**

```
List of MinguoEra :
BEFORE_ROC
ROC
```

**参考：** `https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#eras--`