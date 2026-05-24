# Java 中的 DoubleStream.builder()，示例

> 原文：[https://www.geeksforgeeks.org/doublestream-builder-java-examples/](https://www.geeksforgeeks.org/doublestream-builder-java-examples/)

`DoubleStream.builder()` 返回 `DoubleStream` 的构建器。

## 语法

```java
static DoubleStream.Builder builder()
```

## 参数

1.  **DoubleStream.Builder**：`DoubleStream` 的可变构建器。流构建器有一个生命周期，它从构建阶段开始，在此期间可以添加元素，然后过渡到构建阶段，在此阶段之后可以不添加元素。

## 返回值

该函数返回 `DoubleStream` 的构建器。

## 例 1

```java
// Java code for DoubleStream builder()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream using
        // DoubleStream builder()
        DoubleStream stream = DoubleStream.builder()
                                          .add(2.3)
                                          .build();

        // Displaying the elements
        stream.forEach(System.out::println);
    }
}
```

输出：

```java
2.3
```

## 例 2

```java
// Java code for DoubleStream builder()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream using
        // DoubleStream builder()
        DoubleStream stream = DoubleStream.builder().
        add(2.3).add(-1.2).add(3.5).add(10.74).build();

        // Displaying the elements
        stream.forEach(System.out::println);
    }
}
```

输出：

```java
2.3
-1.2
3.5
10.74
```