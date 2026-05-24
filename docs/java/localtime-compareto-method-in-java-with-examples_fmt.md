# Java 中的 `LocalTime` `compareTo()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/localtime-compareto-method-in-java-with-examples/](https://www.geeksforgeeks.org/localtime-compareto-method-in-java-with-examples/)

`LocalTime` 类的 `compareTo()` 方法用于将这个 `LocalTime` 对象与作为参数传递的 `LocalTime` 进行比较，以检查两个 `LocalTime` 是否相等。两个本地时间之间的比较基于一天内本地时间的时间线位置。该方法返回的值确定如下：

*   如果 `LocalTime` 大于作为参数传递的 `LocalTime`，则返回一个正值。
*   如果 `LocalTime` 等于作为参数传递的 `LocalTime`，则返回零 (0)。
*   如果 `LocalTime` 小于作为参数传递的 `LocalTime`，则返回一个负值。

## 语法

```java
public int compareTo(LocalTime other)
```

## 参数

该方法接受单个参数 `LocalTime`，即要比较的另一个 `LocalTime`，不应该为 `null`。

## 返回值

该方法返回一个 `int` 值，返回值确定如下：

*   如果此 `LocalTime` 大于作为参数传递的 `LocalTime`，则返回正值。
*   如果此 `LocalTime` 等于作为参数传递的 `LocalTime`，则返回零 (0)。
*   如果此 `LocalTime` 小于作为参数传递的 `LocalTime`，则返回负值。

下面的程序说明了 `compareTo()` 方法：

### 程序 1：当该本地时间大于

```java
// Java program to demonstrate
// LocalTime.compareTo() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Objects
        LocalTime time1
            = LocalTime.parse("17:52:49");
        LocalTime time2
            = LocalTime.parse("13:08:00");

        // apply compareTo()
        int value = time1.compareTo(time2);

        // print LocalDateTime
        System.out.println("Int Value:" + value);

        if (value > 0)
            System.out.println("LocalTime1 is greater");
        else if (value == 0)
            System.out.println("LocalTime1 is equal to"
                               + " LocalTime2");
        else
            System.out.println("LocalTime2 is greater");
    }
}
```

**输出：**

```java
Int Value:1
LocalTime1 is greater
```

### 程序 2：当该本地时间小于

```java
// Java program to demonstrate
// LocalTime.compareTo() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Objects
        LocalTime time1
            = LocalTime.parse("07:12:29");
        LocalTime time2
            = LocalTime.parse("13:08:00");

        // apply compareTo()
        int value = time1.compareTo(time2);

        // print LocalDateTime
        System.out.println("Int Value:" + value);

        if (value > 0)
            System.out.println("LocalTime1 is greater");
        else if (value == 0)
            System.out.println("LocalTime1 is equal to"
                               + " LocalTime2");
        else
            System.out.println("LocalTime2 is greater");
    }
}
```

**输出：**

```java
Int Value:-1
LocalTime2 is greater
```

### 程序 3：当两个本地时间相等时

```java
// Java program to demonstrate
// LocalTime.compareTo() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Objects
        LocalTime time1
            = LocalTime.parse("13:08:00");
        LocalTime time2
            = LocalTime.parse("13:08:00");

        // apply compareTo()
        int value = time1.compareTo(time2);

        // print LocalDateTime
        System.out.println("Int Value:" + value);

        if (value > 0)
            System.out.println("LocalTime1 is greater");
        else if (value == 0)
            System.out.println("LocalTime1 is equal to"
                               + " LocalTime2");
        else
            System.out.println("LocalTime2 is greater");
    }
}
```

**输出：**

```java
Int Value:0
LocalTime1 is equal to LocalTime2
```

**参考：** [https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#compareTo(java.time.LocalTime)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#compareTo(java.time.LocalTime))