# Java 中的 `sequential()`

> 原文: [https://www.geeksforgeeks.org/doublestream-sequential-java/](https://www.geeksforgeeks.org/doublestream-sequential-java/)

`DoubleStream sequential()` 返回顺序双流。它可能会自己返回，要么是因为流已经是顺序的，要么是因为基础流状态被修改为顺序的。

`sequential()` 是一个中间操作。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

## 语法

```java
DoubleStream sequential()
```
其中，`DoubleStream` 是一个原始双精度值元素序列。

## 返回值
一个连续的双流。

## 示例 1
`sequential()` 返回顺序双流。

```java
// Java code for DoubleStream sequential()
// to return a sequential DoubleStream.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(3.3, 5.4, 9.2,
                                              12.1, 14.4);

        // Using DoubleStream sequential()
        DoubleStream streamNew = stream.sequential();

        // Displaying sequential DoubleStream
        streamNew.forEach(System.out::println);
    }
}
```

**Output:**
```java
3.3
5.4
9.2
12.1
14.4
```

## 示例 2
空双流上的 `sequential()`。

```java
// Java code for DoubleStream sequential()
// on empty DoubleStream
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an empty DoubleStream
        DoubleStream stream = DoubleStream.empty();

        // To check if it is parallel or not
        System.out.println("parallel : " + stream.isParallel());

        stream = stream.parallel();

        // To check if it is parallel or not
        System.out.println("parallel : " + stream.isParallel());

        stream = stream.sequential();

        // To check if it is parallel or not
        System.out.println("parallel : " + stream.isParallel());
    }
}
```

**Output:**
```java
parallel : false
parallel : true
parallel : false
```