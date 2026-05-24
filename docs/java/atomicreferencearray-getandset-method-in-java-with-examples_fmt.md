# Java 中的 AtomicReferenceArray getAndSet()方法，示例

> 原文：[https://www.geeksforgeeks.org/atomicreferencearray-getandset-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomicreferencearray-getandset-method-in-java-with-examples/)

`AtomicReferenceArray` 类的 `getAndSet()` 方法用于将 `AtomicReferenceArray` 对象的索引 `i` 的值原子地设置为 `newValue`，`newValue` 作为参数传递，并返回 `AtomicReferenceArray` 对象的旧值。内存效果由 `VarHandle.getAndSet()` 指定，该方法指定该变量作为内存语义进行处理，就像该变量被声明为 `volatile` 一样。

**语法：**

```java
public final E getAndSet(int i, E newValue)
```

**参数：** 该方法接受：
*   `i` 是执行操作的原子引用数组的索引，
*   `newValue` 是要设置的新值。

**返回值：** 此方法返回索引 `i` 的旧值。

下面的程序说明了 `getAndSet()` 方法：

## 程序 1

```java
// Java program to demonstrate
// AtomicReferenceArray.getAndSet() method

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

        // apply getAndSet()
        int oldV1 = ref.getAndSet(0, 8913);
        int oldV2 = ref.getAndSet(1, 6543);

        // print
        System.out.println("Old value at index 0: "
                           + oldV1);
        System.out.println("New value at index 0: "
                           + ref.get(0));
        System.out.println("Old value at index 1: "
                           + oldV2);
        System.out.println("New value at index 1: "
                           + ref.get(1));
    }
}
```

**Output：**

```java
Old value at index 0: 1234
New value at index 0: 8913
Old value at index 1: 4322
New value at index 1: 6543
```

## 程序 2

```java
// Java program to demonstrate
// AtomicReferenceArray.getAndSet() method

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

        // apply getAndSet()
        String oldV1
            = ref.getAndSet(0, "GEEKS FOR GEEKS");
        String oldV2
            = ref.getAndSet(1, "JAVA SCRIPT");

        // print
        System.out.println(
            "Old value at index 0: "
            + oldV1);
        System.out.println(
            "New value at index 0: "
            + ref.get(0));
        System.out.println(
            "Old value at index 1: "
            + oldV2);
        System.out.println(
            "New value at index 1: "
            + ref.get(1));
    }
}
```

**Output：**

```java
Old value at index 0: GFG
New value at index 0: GEEKS FOR GEEKS
Old value at index 1: JS
New value at index 1: JAVA SCRIPT
```

**参考文献：** [https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReferenceArray.html#getAndSet](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReferenceArray.html#getAndSet)