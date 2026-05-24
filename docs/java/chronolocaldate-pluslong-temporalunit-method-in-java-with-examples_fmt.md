## Java 中的 `ChronoLocalDate plus(long, TemporalUnit)` 方法示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldate-pluslong-temporalunit-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-pluslong-temporalunit-method-in-java-with-examples/)

`ChronoLocalDate` 接口的 `plus(long, TemporalUnit)` 方法用于返回该日期的副本，并在其中添加指定数量的单位。如果无法添加该数量（例如因为不支持该单位或其他原因），则会抛出异常。此实例是不可变的，不受此方法调用的影响。

### 语法
```java
public ChronoLocalDate plus(long amountToAdd,
                      TemporalUnit unit)
```

### 参数
此方法接受两个参数：
*   `amountToAdd`：要添加到结果中的单位数量，可以是负数。
*   `unit`：要添加的单位。

### 返回值
该方法基于该日期时间返回一个添加了指定数量的 `ChronoLocalDate`。

下面的程序说明了 `plus()` 方法：

### 程序 1
```java
// Java program to demonstrate
// ChronoLocalDate.plus() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

// create a ChronoLocalDate object
        ChronoLocalDate zonedlt
            = LocalDate.parse("2018-12-06");

// add 300 Months to ChronoLocalDate
        ChronoLocalDate value
            = zonedlt.plus(300, ChronoUnit.MONTHS);

// print result
        System.out.println("ChronoLocalDate after adding Months : "
                           + value);
    }
}
```

### 输出
```java
ChronoLocalDate after adding Months : 2043-12-06
```

### 参考文献
T2