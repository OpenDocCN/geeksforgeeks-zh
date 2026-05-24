# Java 中的 DoubleAdder floatValue() 方法示例

> 原文：`https://www.geeksforgeeks.org/doubleadder-floatvalue-method-in-java-with-examples/`

`DoubleAdder.floatValue()` 是 `java` 中的一个内置方法，它在缩小原语转换后将 `sum()` 作为 `float` 返回。创建类的对象时，其初始值为零。

## 语法

```java
public float floatValue()
```

## 参数

该方法不接受任何参数。

## 返回值

方法返回转换为浮点数据类型后该对象表示的数值。

## 程序说明

下面的程序说明了上面的方法：

```java
// Program to demonstrate the floatValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(11);
        num.add(10);

        // floatValue() operation on variable num
        num.floatValue();

        // Print after floatValue() operation
        System.out.println("the value after floatValue() is: " + num);
    }
}
```

## 输出

```java
the value after floatValue() is: 21.0
```

```java
// Program to demonstrate the floatValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(10);

        // floatValue() operation on variable num
        num.floatValue();

        // Print after floatValue() operation
        System.out.println("the value after floatValue() is: " + num);
    }
}
```

## 输出

```java
the value after floatValue() is: 10.0
```

## 参考

`https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/DoubleAdder.html#floatValue--`