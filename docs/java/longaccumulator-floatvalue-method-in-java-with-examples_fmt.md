# Java 中 LongAccumulator.floatValue() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/longaccumulator-floatvalue-method-in-java-with-examples/](https://www.geeksforgeeks.org/longaccumulator-floatvalue-method-in-java-with-examples/)

`java.lang.LongAccumulator.floatValue()` 是 Java 中的一个内置方法，它在扩展原语转换后以浮点形式返回当前值。

## 语法：
```java
public float floatValue()
```

## 参数：
该方法不接受任何参数。

## 返回值：
该方法在一个加宽的原语转换后，以浮点形式返回当前值。

下面的程序说明了上述方法：

## 程序 1：
```java
// Program to demonstrate the floatValue() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(42);
        num.accumulate(10);

        // Print before floatValue operation
        System.out.println(" the old value is: " + num);

        // floatValue's current value
        num.floatValue();

        // Print after floatValue operation
        System.out.println(" the current value is: " + num);
    }
}
```

## 输出：
```java
the old value is: 52
 the current value is: 52
```

## 程序 2：
```java
// Program to demonstrate the floatValue() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(4);
        num.accumulate(15);

        // Print before floatValue operation
        System.out.println(" the old value is: " + num);

        // floatValue's current value
        num.floatValue();

        // Print after floatValue operation
        System.out.println(" the current value is: " + num);
    }
}
```

## 输出：
```java
the old value is: 19
 the current value is: 19
```

## 参考：
[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#floatValue--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#floatValue--)