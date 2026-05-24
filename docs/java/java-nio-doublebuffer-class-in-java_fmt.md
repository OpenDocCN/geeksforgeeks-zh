# Java 中的 DoubleBuffer 类

> 原文：[https://www.geeksforgeeks.org/java-nio-doublebuffer-class-in-java/](https://www.geeksforgeeks.org/java-nio-doublebuffer-class-in-java/)

**双缓冲区**保存输入/输出操作中使用的一系列双精度值。`DoubleBuffer` 类为双精度缓冲区提供了以下四类操作：

*   读取双精度的绝对和相对 `get` 方法。
*   写入双精度的绝对和相对 `put` 方法。
*   相对大容量 `put` 和 `get` 方法，用于将连续的 `double` 序列从 `double` 数组或其他 `double` 缓冲区传输到该缓冲区，并从该缓冲区传输到数组。

`DoubleBuffer` 可以通过以下方式创建：

*   `allocate()`：这为缓冲区的内容分配空间。
*   `wrap()`：这将现有的 `double` 数组包装到缓冲区中。

`DoubleBuffer` 类的大多数方法直接类似于 `ByteBuffer` 定义的方法。

## 类别申报

```java
public abstract class DoubleBuffer
    extends Buffer
    implements Comparable<DoubleBuffer>
```

## DoubleBuffer 类的方法

| 方法 | 描述 |
| --- | --- |
| [`allocate(int capacity)`](https://www.geeksforgeeks.org/doublebuffer-allocate-method-in-java-with-examples/) | 这个方法分配一个新的双缓冲区。 |
| [`array()`](https://www.geeksforgeeks.org/doublebuffer-array-method-in-java-with-examples/) | 此方法返回支持此缓冲区的 `double` 数组。 |
| [`arrayOffset()`](https://www.geeksforgeeks.org/doublebuffer-arrayoffset-method-in-java-with-examples/) | 此方法返回缓冲区第一个元素在该缓冲区后备数组中的偏移量。 |
| [`asReadOnlyBuffer()`](https://www.geeksforgeeks.org/doublebuffer-asreadonlybuffer-method-in-java-with-examples/) | 此方法创建一个新的只读 `DoubleBuffer`，共享该缓冲区的内容。 |
| [`compact()`](https://www.geeksforgeeks.org/doublebuffer-compact-method-in-java-with-examples/) | 这个方法压缩这个缓冲区。 |
| [`compareTo(DoubleBuffer)`](https://www.geeksforgeeks.org/doublebuffer-compareto-method-in-java-with-examples/) | 此方法将此缓冲区与另一个缓冲区进行比较。 |
| [`duplicate()`](https://www.geeksforgeeks.org/doublebuffer-duplicate-method-in-java-with-examples/) | 此方法创建一个新的 `DoubleBuffer`，共享该缓冲区的内容。 |
| [`equals(Object ob)`](https://www.geeksforgeeks.org/doublebuffer-equals-method-in-java-with-examples/) | 这个方法告诉这个缓冲区是否等于另一个对象。 |
| [`get()`](https://www.geeksforgeeks.org/doublebuffer-get-methods-in-java-with-examples/) | 这个方法是一个相对 `get` 方法，在缓冲区的当前位置返回 `double`。 |
| [`get(double[] dst)`](https://www.geeksforgeeks.org/doublebuffer-get-methods-in-java-with-examples/) | 这个方法是一个相对的批量 `get` 方法，并返回这个缓冲区。 |
| [`get(double[] dst, int offset, int length)`](https://www.geeksforgeeks.org/doublebuffer-get-methods-in-java-with-examples/) | 这个方法是一个相对的批量 `get` 方法和这个缓冲区。 |
| [`get(int index)`](https://www.geeksforgeeks.org/doublebuffer-get-methods-in-java-with-examples/) | 这个方法是一个绝对的 `get` 方法和这个缓冲区。 |
| [`hasArray()`](https://www.geeksforgeeks.org/doublebuffer-hasarray-method-in-java-with-examples/) | 此方法告知此缓冲区是否由可访问的 `double` 数组支持。 |
| [`hashCode()`](https://www.geeksforgeeks.org/doublebuffer-hashcode-method-in-java-with-examples/) | 此方法返回此缓冲区的当前哈希代码。 |
| [`isDirect()`](https://www.geeksforgeeks.org/doublebuffer-ismethod-in-java-with-examples/) | 这个方法告诉这个 `DoubleBuffer` 是否是直接的。 |
| [`order()`](https://www.geeksforgeeks.org/doublebuffer-order-methods-in-java-with-examples/) | 此方法检索此缓冲区的字节顺序。 |
| [`put(double d)`](https://www.geeksforgeeks.org/doublebuffer-put-methods-in-java-with-examples-set-1/) | 这个方法是一个相对 `put` 方法，返回这个缓冲区。 |
| [`put(double[] src)`](https://www.geeksforgeeks.org/doublebuffer-put-methods-in-java-with-examples-set-1/) | 这个方法是一个相对大容量的 `put` 方法，并返回这个缓冲区。 |
| [`put(double[] src, int offset, int length)`](https://www.geeksforgeeks.org/doublebuffer-put-methods-in-java-with-examples-set-1/) | 这个方法是一个相对大容量的 `put` 方法，并返回这个缓冲区。 |
| [`put(DoubleBuffer src)`](https://www.geeksforgeeks.org/doublebuffer-put-methods-in-java-with-examples-set-1/) | 这个方法是一个相对大容量的 `put` 方法，并返回这个缓冲区。 |
| [`put(int index, double d)`](https://www.geeksforgeeks.org/doublebuffer-put-methods-in-java-with-examples-set-1/) | 此方法是此缓冲区的绝对 `put` 方法。 |
| [`slice()`](https://www.geeksforgeeks.org/doublebuffer-slice-method-in-java-with-examples/) | 此方法创建一个新的 `DoubleBuffer`，其内容是该缓冲区内容的共享子序列。 |
| [`toString()`](https://www.geeksforgeeks.org/doublebuffer-tostring-method-in-java-with-examples/) | 这个方法返回一个总结这个缓冲区状态的字符串。 |
| [`wrap(double[] array)`](https://www.geeksforgeeks.org/doublebuffer-wrap-method-in-java-with-examples/) | 此方法将 `double` 数组包装到缓冲区中。 |
| [`wrap(double[] array, int offset, int length)`](https://www.geeksforgeeks.org/doublebuffer-wrap-method-in-java-with-examples/) | 此方法将 `double` 数组包装到缓冲区中。 |

## 示例程序

下面是一些演示 `DoubleBuffer` 类及其方法的程序：

### 例 1

```java
// Java program to demonstrate
// DoubleBuffer class

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // Declaring the capacity of the DoubleBuffer
        int capacity = 5;

        // Creating the DoubleBuffer
        // creating object of DoubleBuffer and allocating size capacity
        DoubleBuffer db = DoubleBuffer.allocate(capacity);

        // putting the value in DoubleBuffer
        db.put(9.26F);
        db.put(2, 5.61F);

        System.out.println("DoubleBuffer: "
                           + Arrays.toString(db.array()));
    }
}
```

**Output**

```java
DoubleBuffer: [9.260000228881836, 0.0, 5.610000133514404, 0.0, 0.0]
```

### 例 2

```java
// Java program to demonstrate
// DoubleBuffer class

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // Declare and initialize the double array
        double[] fbb = { 1.25D, 5.34D, 8.56D };

        // print the double array length
        System.out.println("Array length : " + fbb.length);

        // print the double array element
        System.out.println("\nArray element : "
                           + Arrays.toString(fbb));

        // wrap the double array into DoubleBuffer
        // using wrap() method
        DoubleBuffer doubleBuffer = DoubleBuffer.wrap(fbb);

        // Rewind the DoubleBuffer
        doubleBuffer.rewind();

        // print the DoubleBuffer
        System.out.println(
            "\ndoubleBuffer : "
            + Arrays.toString(doubleBuffer.array()));

        // print the DoubleBuffer capacity
        System.out.println("\ndoubleBuffer capacity : "
                           + doubleBuffer.capacity());

        // print the DoubleBuffer position
        System.out.println("\ndoubleBuffer position: "
                           + doubleBuffer.position());
    }
}
```

**Output**

```java
Array length : 3

Array element : [1.25, 5.34, 8.56]

doubleBuffer : [1.25, 5.34, 8.56]

doubleBuffer capacity : 3

doubleBuffer position: 0
```