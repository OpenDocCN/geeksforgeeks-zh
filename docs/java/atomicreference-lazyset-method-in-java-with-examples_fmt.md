# Java 中的 AtomicReference lazySet()方法，带示例

> 原文：[https://www.geeksforgeeks.org/atomicreference-lazyset-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomicreference-lazyset-method-in-java-with-examples/)

一个`AtomicReference`类的`lazySet()`方法用于设置这个原子引用对象的值，该对象具有由`VarHandle.setRelease()`指定的内存效果，以确保先前的加载和存储在这次访问后不会被重新排序。

## 语法

```java
public final void lazySet(V newValue)
```

## 参数
此方法接受新值，即要设置的新值。

## 返回值
此方法不返回任何内容。

下面的程序说明了`lazySet()`方法：

### 程序 1

```java
// Java program to demonstrate
// AtomicReference.lazySet() method
import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {
        // create an atomic reference object.
        AtomicReference<Integer> ref
            = new AtomicReference<Integer>();

        // set some value using lazySet method
        ref.lazySet(67545678);

        // print value
        System.out.println("Integer value = "
                           + ref.get());
    }
}
```

**Output:**

```java
Integer value = 67545678
```

### 程序 2

```java
// Java program to demonstrate
// AtomicReference.lazySet() method
import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {
        // create an atomic reference object
        AtomicReference<String> ref
            = new AtomicReference<String>();

        // set some value using lazySet()
        ref.lazySet("GFG(GeeksForGeeks)");

        // print value
        System.out.println(ref.get());
    }
}
```

**Output:**

```java
GFG(GeeksForGeeks)
```

## 参考文献
[https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReference.html#lazySet(V)](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReference.html#lazySet(V))