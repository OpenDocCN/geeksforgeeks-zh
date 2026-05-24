# Java 中的 MinguoDate.now() 方法示例

> 原文：[https://www.geeksforgeeks.org/minguodate-now-method-in-java-with-example/](https://www.geeksforgeeks.org/minguodate-now-method-in-java-with-example/)

`java.time.chrono.MinguoDate` 类的 `now()` 方法，用于从指定的时钟获取根据民国日历系统的当前民国日期。

### 语法
```java
public static MinguoDate now(Clock clock)
```

### 参数
该方法取 `Clock` 的对象，在此基础上将形成民国日期。

### 返回值
该方法从指定的时钟根据民国日历系统返回当前的 `MinguoDate`。

以下是举例说明 `now()` 方法：

## 示例 1

```java
// Java program to demonstrate now() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing clock
            Clock clock = Clock.systemUTC();

            // Creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now(clock);

            // Display the result
            System.out.println("MinguoDate: "
                               + hidate);
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

**输出：**
```java
MinguoDate: Minguo ROC 109-04-24
```

## 示例 2

```java
// Java program to demonstrate now() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing clock
            Clock clock = Clock.systemDefaultZone();

            // Creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now(clock);

            // Display the result
            System.out.println("MinguoDate: "
                               + hidate);
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

**输出：**
```java
MinguoDate: Minguo ROC 109-04-24
```

### 参考
[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#now-java.time.Clock-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#now-java.time.Clock-)