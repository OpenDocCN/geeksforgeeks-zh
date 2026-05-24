# Java 中 LongAccumulator.doubleValue() 方法，带示例

> 原文：[https://www.geeksforgeks.org/longaccumulator-doublevalue-method-in-java-with-examples/](https://www.geeksforgeks.org/longaccumulator-doublevalue-method-in-java-with-examples/)

`java.lang.LongAccumulator.doubleValue()` 是 Java 中的一个内置方法，在扩展原语转换后以双精度形式返回当前值。

## 语法
```java
public double doubleValue()
```

## 参数
该方法不接受任何参数。

## 返回值
此方法在加宽原语转换后以双精度形式返回当前值。

下面的程序说明了上述方法：

### 程序 1
```java
// Program to demonstrate the doubleValue() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(42);
        num.accumulate(10);

        // Print before doubleValue operation
        System.out.println(" the old value is: " + num);

        // doubleValues current value
        num.doubleValue();

        // Print after doubleValue operation
        System.out.println("the current value is: " + num);
    }
}
```

**输出：**
```java
the old value is: 52
the current value is: 52
```

### 程序 2
```java
// Program to demonstrate the doubleValue() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(4);
        num.accumulate(10);

        // Print before doubleValue operation
        System.out.println(" the old value is: " + num);

        // doubleValues current value
        num.doubleValue();

        // Print after doubleValue operation
        System.out.println("the current value is: " + num);
    }
}
```

**输出：**
```java
the old value is: 14
the current value is: 14
```

**参考：** [https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#doubleValue--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#doubleValue--)