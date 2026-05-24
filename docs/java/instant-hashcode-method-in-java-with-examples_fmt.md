# Java 中的 Instant hashCode() 方法示例

> 原文：[https://www.geeksforgeeks.org/instant-hashcode-method-in-java-with-examples/](https://www.geeksforgeeks.org/instant-hashcode-method-in-java-with-examples/)

`Instant` 类的 `hashCode()` 方法用于获取该 `Instant` 的 `hashCode`。如果对象没有改变，`hashCode` 总是相同的。`hashCode` 是 JVM 在创建对象时生成的唯一代码。它可以用来对哈希表、哈希表等哈希相关算法进行操作。也可以用对象的唯一代码（`hashCode`）来搜索对象。

## 语法

```java
public int hashCode()
```

## 返回值

该方法返回此 `Instant` 的 `hashCode`。

下面的程序说明了 `Instant.hashCode()` 方法：

## 程序 1

```java
// Java program to demonstrate
// Instant.hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // get hashCode
        // using hashCode()
        int value = instant.hashCode();

        // print result
        System.out.println("hashCode value: "
                           + value);
    }
}
```

## 输出

```java
hashCode value: -683539878
```

## 程序 2

```java
// Java program to demonstrate
// Instant.hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant = Instant.now();

        // current Instant
        System.out.println("Current Instant: "
                           + instant);

        // get hashCode
        // using hashCode()
        int value = instant.hashCode();

        // print result
        System.out.println("hashCode value: "
                           + value);
    }
}
```

## 输出

```java
Current Instant: 2018-11-27T04:45:52.428Z
hashCode value: 1896457472
```

参考文献：[https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#hashCode()](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#hashCode())