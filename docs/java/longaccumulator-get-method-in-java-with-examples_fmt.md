# Java 中 LongAccumulator get() 方法示例

> 原文：[https://www.geeksforgeeks.org/longaccumulator-get-method-in-java-with-examples/](https://www.geeksforgeeks.org/longaccumulator-get-method-in-java-with-examples/)

`java.lang.LongAccumulator.get()` 是 Java 中的一个内置方法，返回 `LongAccumulator` 对象的当前值。

## 语法

```java
public long get()
```

## 参数
该方法不接受任何参数。

## 返回值
该方法返回 `LongAccumulator` 对象的当前值。

下面的程序说明了上述方法：

## 程序 1

```java
// Program to demonstrate the get() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(2);
        num.accumulate(10);

        // Gets current value
        long x = num.get();

        // Print after get operation
        System.out.println(" the current value is: " + x);
    }
}
```

## 输出

```java
the current value is: 12
```

## 程序 2

```java
// Program to demonstrate the get() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(22);
        num.accumulate(10);

        // Gets current value
        long x = num.get();

        // Print after get operation
        System.out.println(" the current value is: " + x);
    }
}
```

## 输出

```java
the current value is: 32
```

## 参考
[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#get--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#get--)