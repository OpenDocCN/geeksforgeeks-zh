# Java 中的 IntStream generate()方法

> 原文：`https://www.geeksforgeks.org/intstream-generate-method-java/`

`IntStream generate(IntSupplier s)` 返回一个无限顺序无序流，其中每个元素都是由提供的 `IntSupplier`（int 值结果的供应商）生成的。这适用于生成恒定流、随机元素流等。

## 语法：

```java
static IntStream generate(IntSupplier s)
```

## 参数：

1.  `IntStream`：原始的 int 值元素序列。
2.  `IntSupplier`：int 值元素的供应商。
3.  `s`：生成元素的 `IntSupplier`。

## 返回值：

一个新的无限顺序无序 `IntStream`。

## 示例 1：生成随机整数流。

```java
// Java code for IntStream.generate()
// to generate an infinite sequential
// unordered IntStream
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // using IntStream.generate() method
        // to generate 7 random Integer values
        IntStream stream = IntStream.generate(()
                -> { return (int)(Math.random() * 10000); });

        // Displaying the randomly generated values
        stream.limit(7).forEach(System.out::println);
    }
}
```

输出：

```java

```