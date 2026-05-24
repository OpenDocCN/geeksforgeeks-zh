# Java 中的 ChronoLocalDate hashCode()方法，带示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldate-hashcode-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-hashcode-method-in-java-with-examples/)

使用 Java 中 `ChronoLocalDate` 接口的 `hashCode()` 方法，以整数形式获取这个 `ChronoLocalDate` 对象的 hashCode 值。

## 语法

```java
public int hashCode()
```

## 参数

该方法不接受任何参数。

## 返回值

函数以整数的形式返回合适的哈希码。

下面的程序说明了 Java 中的 `hashCode()` 方法：

### 程序 1

```java
// Program to illustrate the hashCode() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDate dt
            = LocalDate.parse("2018-11-27");

        // Prints the hash-code
        System.out.println(dt.hashCode());
    }
}
```

**输出:**

```java

```

### 程序二

```java
// Program to illustrate the hashCode() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDate dt
            = LocalDate.parse("2015-12-23");

        // Prints the hash-code
        System.out.println(dt.hashCode());
    }
}
```

**输出:**

```java

```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#hashCode--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#hashCode--)