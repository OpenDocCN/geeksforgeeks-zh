# Java 中的 MonthDay now(Clock)方法，示例

> 原文：[https://www.geeksforgeeks.org/monthday-nowclock-method-in-java-with-examples/](https://www.geeksforgeeks.org/monthday-nowclock-method-in-java-with-examples/)

Java 中 `MonthDay` 类的 `now(Clock clock)` 方法用于从指定的时钟获取当前的月-日。

## 语法

```java
public static MonthDay now(Clock clock)
```

## 参数

此方法接受 `Clock` 作为代表要使用的时钟的参数。

## 返回值

此方法返回当前 `MonthDay`。

下面的程序说明了 Java 中 `MonthDay` 的 `now(Clock)` 方法：

### 程序 1

```java
// Java program to demonstrate
// MonthDay.now(Clock clock) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(Clock clock) method
        // of MonthDay class
        MonthDay result = MonthDay.now(
            Clock.systemUTC());

        // print both month and day
        System.out.println("MonthDay: "
                           + result);
    }
}
```

**输出：**

```
MonthDay: --05-09
```

### 程序 2

```java
// Java program to demonstrate
// MonthDay.now(Clock clock) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(Clock clock) method
        // of MonthDay class
        MonthDay result = MonthDay.now(
            Clock.systemUTC());

        // print only month
        System.out.println("Month: "
                           + result.getMonth());
    }
}
```

**输出：**

```
Month: MAY
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#now(java.time.Clock)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#now(java.time.Clock))