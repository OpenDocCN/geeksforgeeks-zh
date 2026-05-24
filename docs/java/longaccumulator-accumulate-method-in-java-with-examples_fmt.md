# Java 中 `LongAccumulator.accumulate()` 方法示例

> 原文：[https://www.geeksforgeeks.org/longaccumulator-accumulate-method-in-java-with-examples/](https://www.geeksforgeeks.org/longaccumulator-accumulate-method-in-java-with-examples/)

`java.lang.LongAccumulator.accumulate()` 是 Java 中的一个内置方法，用给定的值更新特定的 `LongAccumulator` 对象。

## 语法

```java
public void accumulate(long x)
```

## 参数

该方法接受单个参数 `x`，即当前 `LongAccumulator` 对象更新的值。

## 返回值

该方法返回更新后的值。

下面的程序说明了上述方法：

## 程序 1

```java
// Program to demonstrate the accumulate() method
import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(2);

        // Print after accumulate
        System.out.println("After update the value is: " + num);
    }
}
```

## 输出

```java
After update the value is: 2
```

## 程序 2

```java
// Program to demonstrate the accumulate() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(5);

        // Print after accumulate
        System.out.println("After update the value is: " + num);
    }
}
```

## 输出

```java
After update the value is: 5
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#accumulate-long-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#accumulate-long-)