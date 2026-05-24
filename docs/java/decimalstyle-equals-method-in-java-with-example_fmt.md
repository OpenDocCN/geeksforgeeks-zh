# Java 中的 DecimalStyle.equals() 方法示例

> 原文：[https://www.geeksforgeeks.org/decimalstyle-equals-method-in-java-with-example/](https://www.geeksforgeeks.org/decimalstyle-equals-method-in-java-with-example/)

`java.time.format.DecimalStyle` 类的 `equals()` 方法用于检查这个 `DecimalStyle` 与指定的 `DecimalStyle` 是否相等。此方法采用一个 `DecimalStyle` 实例，并将其与该 `DecimalStyle` 进行比较，然后返回一个表示相同内容的布尔值。

## 语法

```java
public boolean equals(Object obj)
```

## 参数

该方法接受一个参数 `Object obj`，该参数是要检查是否与该 `DecimalStyle` 相等的 `DecimalStyle`。

## 返回值

这个方法返回一个 `boolean`，告诉这个 `DecimalStyle` 是否等于指定的对象。

## 异常

这个方法不抛出任何异常。

## 程序

```java
// Java program to demonstrate
// the above method

import java.time.format.*;
import java.util.*;

public class DecimalStyleDemo {
    public static void main(String[] args)
    {

        DecimalStyle ds1
            = DecimalStyle.STANDARD;

        DecimalStyle ds2
            = DecimalStyle.of(
                new Locale("ENGLISH"));

        DecimalStyle ds3 = null;

        System.out.println("Comparing DS 1 and DS 2: "
                           + ds1.equals(ds2));

        System.out.println("Comparing DS 2 and DS 3: "
                           + ds2.equals(ds3));

        System.out.println("Comparing DS 1 and DS 3: "
                           + ds1.equals(ds3));
    }
}
```

## 输出

```java
Comparing DS 1 and DS 2: true
Comparing DS 2 and DS 3: false
Comparing DS 1 and DS 3: false
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#equals(java.lang.Object)](https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#equals(java.lang.Object))