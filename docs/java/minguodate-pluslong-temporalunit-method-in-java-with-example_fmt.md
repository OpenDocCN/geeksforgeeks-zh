# Java 中的 MinguoDate.plus(long, TemporalUnit) 方法示例

> 原文: [https://www.geeksforgeeks.org/minguodate-pluslong-temporalunit-method-in-java-with-example/](https://www.geeksforgeeks.org/minguodate-pluslong-temporalunit-method-in-java-with-example/)

`java.time.chrono.MinguoDate` 类的 `plus()` 方法，用于在当前的 `MinguoDate` 上加上一定数量的时态取值单位后得到 `MinguoDate`。

**语法:**
```java
public MinguoDate plus(long amount,
                       TemporalUnit unit)
```

**参数**: 该方法以以下参数为参数:
*   `amount`: 为时间单位的 `amount`，与当前民国日期相加。
*   `unit`: 是时间单位或时辰单位的 `TemporalUnit` 对象。

**返回值**: 该方法将当前的民国日期加上一定量的时态取值单位后，返回 `MinguoDate`。

下面举例说明 `plus()` 的方法:

### 示例 1

```java
// Java program to demonstrate
// plus() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.of(1345, 06, 23);

            // display the result
            System.out.println("old Minguo date : "
                               + hidate);

            // adding some amount in Minguo date
            // by using plus() method
            MinguoDate newdate
                = hidate.plus(
                    22,
                    ChronoUnit.DAYS);

            // display the result
            System.out.println("new Minguo date : "
                               + newdate);
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

**Output:**
```java
old Minguo date : Minguo ROC 1345-06-23
new Minguo date : Minguo ROC 1345-07-15
```

### 示例 2

```java
// Java program to demonstrate
// plus() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.of(1345, 06, 23);

            // display the result
            System.out.println("old Minguo date : "
                               + hidate);

            // adding some amount in Minguo date
            // by using plus() method
            MinguoDate newdate
                = hidate.plus(
                    4,
                    ChronoUnit.DECADES);

            // display the result
            System.out.println("new Minguo date : "
                               + newdate);
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

**Output:**
```java
old Minguo date : Minguo ROC 1345-06-23
new Minguo date : Minguo ROC 1385-06-23
```

**参考:** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#plus-long-java.time.temporal.TemporalUnit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#plus-long-java.time.temporal.TemporalUnit-)