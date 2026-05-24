# Java 中的 AtomicReferenceArray compareAndSet() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/atomicreferencearray-compareandset-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomicreferencearray-compareandset-method-in-java-with-examples/)

如果原子引用数组对象的索引 `i` 处的当前值等于预期值，则使用 `AtomicReferenceArray` 类的 `compareAndSet()` 方法自动将原子引用数组的索引 `i` 的值设置为新值。如果更新成功，此方法将返回 `true`。

## 语法

```java
public final boolean
       compareAndSet(
           int i, E expectedValue, E newValue)
```

## 参数

该方法接受：
*   `int i`：作为原子引用数组的索引来执行操作。
*   `E expectedValue`：预期值。
*   `E newValue`：要设置的新值。

## 返回值

如果成功，则该方法返回 `true`，否则返回 `false`，表示实际值与期望值不相等。

下面的程序说明了 `compareAndSet()` 方法：

## 程序 1

```java
// Java program to demonstrate
// compareAndSet() method

import java.util.concurrent.atomic.*;

public class GFG {
    public static void main(String[] args)
    {
        // create an atomic reference object.
        AtomicReferenceArray<Integer> ref
            = new AtomicReferenceArray<Integer>(3);

        // set some value
        ref.set(0, 1234);
        ref.set(1, 4322);

        // apply compareAndSet()
        boolean op1
            = ref.compareAndSet(0, 5434, 8913);
        boolean op2
            = ref.compareAndSet(1, 3236, 6543);

        // print
        System.out.println("Operation at index 0: "
                           + op1);
        System.out.println("Operation at index 0: "
                           + op2);
    }
}
```

**输出：**

```java
Operation at index 0: false
Operation at index 0: false
```

## 程序 2

```java
// Java program to demonstrate
// compareAndSet() method

import java.util.concurrent.atomic.*;

public class GFG {
    public static void main(String[] args)
    {
        // create an atomic reference object.
        AtomicReferenceArray<String> ref
            = new AtomicReferenceArray<String>(3);

        // set some value
        ref.set(0, "GFG");
        ref.set(1, "JS");

        // apply compareAndSet()
        boolean op1
            = ref.compareAndSet(
                0, "GFG",
                "GEEKS FOR GEEKS");
        boolean op2
            = ref.compareAndSet(
                1, "JS",
                "JAVA SCRIPT");

        // print
        System.out.println("Operation at index 0: "
                           + op1);
        System.out.println("New value at index 0: "
                           + ref.get(0));
        System.out.println("Operation at index 1: "
                           + op2);
        System.out.println("New value at index 1: "
                           + ref.get(1));
    }
}
```

**输出：**

```java
Operation at index 0: true
New value at index 0: GEEKS FOR GEEKS
Operation at index 1: true
New value at index 1: JAVA SCRIPT
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReferenceArray.html#compareAndSet(int,E,E)](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReferenceArray.html#compareAndSet(int,E,E))