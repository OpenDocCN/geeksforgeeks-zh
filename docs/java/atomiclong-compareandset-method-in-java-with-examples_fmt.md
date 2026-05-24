# Java中的AtomicLong compareAndSet()方法

> 原文：[https://www.geeksforgeeks.org/atomiclong-compareandset-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomiclong-compareandset-method-in-java-with-examples/)

`java.util.concurrent.atomic.AtomicLong.compareAndSet()`是Java中的一个内置方法，如果当前值等于也在参数中传递的预期值，则将该值设置为参数中传递的值。该函数返回一个布尔值，它告诉我们更新是否完成。

## 语法

```java
public final boolean compareAndSet(long expect,
                                   long val)
```

## 参数

函数接受两个强制参数，描述如下：

*   `expect`：指定原子对象应有的值。
*   `val`：指定当原子整数等于预期值时要更新的值。

## 返回值

函数返回一个布尔值，成功则返回`true`，否则返回`false`。

## 示例

下面的程序说明了上述方法：

### 程序1

```java
// Java program that demonstrates
// the compareAndSet() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {
        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Checks if previous value was 0
        // and then updates it
        boolean res = val.compareAndSet(0, 6);

        // Checks if the value was updated.
        if (res)
            System.out.println("The value was "
                               + "updated and it is "
                               + val);
        else
            System.out.println("The value was "
                               + "not updated");
    }
}
```

**输出：**

```java
Previous value: 0
The value was updated and it is 6
```

### 程序2

```java
// Java program that demonstrates
// the compareAndSet() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {
        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Checks if previous value was 0
        // and then updates it
        boolean res = val.compareAndSet(10, 6);

        // Checks if the value was updated.
        if (res)
            System.out.println("The value was "
                               + "updated and it is "
                               + val);
        else
            System.out.println("The value was "
                               + "not updated");
    }
}
```

**输出：**

```java
Previous value: 0
The value was not updated
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#weakCompareAndSet--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#weakCompareAndSet--)