# DoubleStream empty()

> 原文：[https://www.geeksforgeeks.org/doublestream-empty-java-examples/](https://www.geeksforgeeks.org/doublestream-empty-java-examples/)

`DoubleStream empty()` 是 `java.util.stream.DoubleStream` 中的一个方法，这个方法返回一个空的顺序 `DoubleStream`。

## 语法

```java
static DoubleStream empty()
```
其中，`DoubleStream` 是一个原始双精度值元素的序列，该方法返回一个空的顺序流。

## 例 1

```java
// Java code for DoubleStream empty()
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating an empty DoubleStream, a sequence of
        // primitive double-valued elements
        DoubleStream stream = DoubleStream.empty();

        // Displaying an empty sequential stream
        System.out.println(stream.count());
    }
}
```

**输出：**

```java
0
```

## 例 2

```java
// Java code for DoubleStream empty()
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating an empty DoubleStream, a sequence of
        // primitive double-valued elements
        DoubleStream stream = DoubleStream.empty();

        // Displaying an empty sequential stream
        System.out.println(Arrays.toString(stream.toArray()));
    }
}
```

**输出：**

```java
[]
```