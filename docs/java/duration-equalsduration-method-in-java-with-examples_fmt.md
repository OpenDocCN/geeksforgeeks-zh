# Duration.equals() 方法详解与示例

> 原文: [https://www.geeksforgeeks.org/duration-equalsduration-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-equalsduration-method-in-java-with-examples/)

`java.time` 包中 `Duration` 类的 `equals(Duration)` 方法用于检查这个 `Duration` 是否等于作为参数传递的 `Duration`。

## 语法

```java
public boolean equals(Duration otherDuration)
```

## 参数

该方法接受参数 `otherDuration`，该持续时间将与该持续时间进行比较。

## 返回值

该方法返回一个 `boolean` 值，显示该持续时间是否等于其他持续时间。

以下示例说明了 `Duration.equals()` 方法:

## 例 1

```java
// Java code to illustrate equals() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Duration using ofDays() method
        Duration duration2
            = Duration.ofDays(10);

        // Compare the durations
        // using equals() method
        System.out.println(duration1
                           .equals(duration2));
    }
}
```

**输出:**

```java
false
```

## 例 2

```java
// Java code to illustrate equals() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofHours() method
        Duration duration1
            = Duration.ofHours(5);

        // Duration using ofHours() method
        Duration duration2
            = Duration.ofHours(5);

        // Compare the durations
        // using equals() method
        System.out.println(duration1
                           .equals(duration2));
    }
}
```

**输出:**

```java
true
```

## 例 3

```java
// Java code to illustrate equals() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofDays() method
        Duration duration1
            = Duration.ofDays(5);

        // Duration using ofHours() method
        Duration duration2
            = Duration.ofHours(5);

        // Compare the durations
        // using equals() method
        System.out.println(duration1
                           .equals(duration2));
    }
}
```

**输出:**

```java
false
```

## 参考

[Oracle 文档](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#equals-java.lang.Object-)