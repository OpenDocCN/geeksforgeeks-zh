# MinguoDate.now(ZoneId) 方法示例

> 原文：[`https://www.geeksforgeeks.org/minguodate-nowzoneid-method-in-java-with-examples/`](https://www.geeksforgeeks.org/minguodate-nowzoneid-method-in-java-with-examples/)

`MinguoDate.now(ZoneId)` 方法用于根据指定时区的民国日历系统获取当前的民国日期。

## 语法

```java
public static MinguoDate now(ZoneId zone)
```

## 参数

该方法以 `ZoneId` 对象为参数，在此基础上形成民国日期。

## 返回值

此方法从指定时区根据民国日历系统返回当前的 `MinguoDate`。

以下是 `now()` 方法的示例：

### 示例 1

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

// Creating and initializing ZoneId
            ZoneId id = ZoneId.systemDefault();

// Creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now(id);

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

### 示例 2

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

// Creating and initializing ZoneId
            ZoneId id = ZoneId.of("Z");

// Creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now(id);

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

## 参考

[`https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#now-java.time.ZoneId-`](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#now-java.time.ZoneId-)