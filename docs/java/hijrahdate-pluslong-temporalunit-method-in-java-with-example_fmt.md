# Java 中的 `HijrahDate.plus(long, TemporalUnit)` 方法示例

> 原文: [https://www.geeksforgeeks.org/hijrahdate-pluslong-temporalunit-method-in-java-with-example/](https://www.geeksforgeeks.org/hijrahdate-pluslong-temporalunit-method-in-java-with-example/)

`java.time.chrono.HijrahDate` 类的 `plus()` 方法用于在当前 hijrah date 上添加一定数量的时态存取单元后获取 hijrah date。

**语法:**

```java
public HijrahDate plus(long amount,
                       TemporalUnit unit)
```

**参数**: 该方法以以下参数为参数:
*   `amount`: 是时间单位的金额，将与当前回历日期相加。
*   `unit`: 是时间单位或时辰单位的对象。

**返回值**: 该方法在当前回历日期加上一定量的时间存取器单位后，返回 `HijrahDate`。

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
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.of(1345, 06, 23);

            // display the result
            System.out.println("old hijrah date : "
                               + hidate);

            // adding some amount in hijrah date
            // by using plus() method
            HijrahDate newdate
                = hidate.plus(
                    22,
                    ChronoUnit.DAYS);

            // display the result
            System.out.println("new hijrah date : "
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
old hijrah date : Hijrah-umalqura AH 1345-06-23
new hijrah date : Hijrah-umalqura AH 1345-07-16
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
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.of(1345, 06, 23);

            // display the result
            System.out.println("old hijrah date : "
                               + hidate);

            // adding some amount in hijrah date
            // by using plus() method
            HijrahDate newdate
                = hidate.plus(
                    4,
                    ChronoUnit.DECADES);

            // display the result
            System.out.println("new hijrah date : "
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
old hijrah date : Hijrah-umalqura AH 1345-06-23
new hijrah date : Hijrah-umalqura AH 1385-06-23
```

**参考:** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#plus-long-java.time.temporal.TemporalUnit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#plus-long-java.time.temporal.TemporalUnit-)