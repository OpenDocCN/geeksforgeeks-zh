# Java 中的 Duration toDays()方法，示例

> 原文:[https://www.geeksforgeks.org/duration-todays-method-in-java-with-examples/](https://www.geeksforgeks.org/duration-todays-method-in-java-with-examples/)

`java.time`包中`Duration`类的`toDays()`方法用于获取该持续时间的天数值。

## 语法:

```java
public long toDays()
```

## 参数:
该方法不接受任何参数。

## 返回值:
该方法返回一个`long`值，即该时长内的天数。

下面的例子说明了`Duration.toDays()`方法:

## 例 1:

```java
// Java code to illustrate toDays() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        System.out.println("Duration: "
                           + duration);

        // Get the number of days
        // using toDays() method
        System.out.println(duration.toDays());
    }
}
```

## 输出:

```java
Duration: PT51H4M
```

## 例 2:

```java
// Java code to illustrate toDays() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofDays() method
        Duration duration
            = Duration.ofDays(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of days
        // using toDays() method
        System.out.println(duration.toDays());
    }
}
```

## 输出:

```java
Duration: PT240H
```

## 参考:
[https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toDays--](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toDays--)