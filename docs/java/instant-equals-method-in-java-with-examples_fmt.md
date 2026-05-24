# Java 中的 Instant equals()方法，示例

> 原文：[https://www.geeksforgeeks.org/instant-equals-method-in-java-with-examples/](https://www.geeksforgeeks.org/instant-equals-method-in-java-with-examples/)

`Instant`类的`equals(Object otherInstant)`方法用于将此`Instant`与作为参数传递的`Instant`对象进行比较。两个实例之间的比较是基于时刻的时间线位置。该方法返回的值确定如下：

*   如果两个实例相等，则返回`true`。
*   如果两个实例不相等，则返回`false`。

## 语法

```java
public boolean equals(Object otherInstant)
```

## 参数

该方法接受一个强制参数`otherInstant`，即需要比较的另一个时刻，不应该为`null`。

## 返回值

该方法返回一个布尔值，如下所示：

*   `true`：如果两个实例相等。
*   `false`：如果两个实例不相等。

下面的程序说明了`Instant.equals()`方法：

## 程序 1：当两个实例相等时

```java
// Java program to demonstrate
// Instant.equals() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create two instance objects
        Instant instant1
            = Instant.parse("2018-10-20T16:55:30.00Z");

        Instant instant2
            = Instant.parse("2018-10-20T16:55:30.00Z");

        // print Instant Values
        System.out.println("Instant1: "
                           + instant1);
        System.out.println("Instant2: "
                           + instant2);

        // compare both instant
        boolean value = instant1.equals(instant2);

        // print results
        System.out.println("Are both instants are equal: "
                           + value);
    }
}
```

## 输出

```java
Instant1: 2018-10-20T16:55:30Z
Instant2: 2018-10-20T16:55:30Z
Are both instants are equal: true
```

## 程序 2：当两个实例不相等时

```java
// Java program to demonstrate
// Instant.equals() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create two instance objects
        Instant instant1
            = Instant.parse("2018-10-20T16:55:30.00Z");

        Instant instant2
            = Instant.parse("2011-10-20T16:55:30.00Z");

        // print Instant Values
        System.out.println("Instant1: "
                           + instant1);
        System.out.println("Instant2: "
                           + instant2);

        // compare both instant
        boolean value = instant1.equals(instant2);

        // print results
        System.out.println("Are both instants are equal: "
                           + value);
    }
}
```

## 输出

```java
Instant1: 2018-10-20T16:55:30Z
Instant2: 2011-10-20T16:55:30Z
Are both instants are equal: false
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#equals(java.lang.Object)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#equals(java.lang.Object))