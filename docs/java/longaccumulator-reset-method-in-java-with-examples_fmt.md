# Java 中 LongAccumulator reset()方法示例

> 原文：[https://www.geeksforgeeks.org/longaccumulator-reset-method-in-java-with-examples/](https://www.geeksforgeeks.org/longaccumulator-reset-method-in-java-with-examples/)

`java.lang.LongAccumulator.reset()` 是 Java 中的一个内置方法，用于重置变量，同时保持对标识值的更新。

**语法：**

```java
public void reset()
```

**参数：** 该方法不接受任何参数。

**返回值：** 该方法返回复位值。

下面的程序说明了上述方法：

**程序 1：**

```java
// Program to demonstrate the reset() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(2);
        num.accumulate(10);

        // resets current value
        num.reset();

        // Print after reset operation
        System.out.println(" the current value is: " + num);
    }
}
```

**输出：**

```java
the current value is: 0
```

**程序 2：**

```java
// Program to demonstrate the reset() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(42);
        num.accumulate(10);

        // resets current value
        num.reset();

        // Print after reset operation
        System.out.println(" the current value is: " + num);
    }
}
```

**输出：**

```java
the current value is: 0
```

**参考：** [https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#reset--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#reset--)