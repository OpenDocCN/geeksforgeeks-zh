# IntStream.Builder build() 方法详解

> 原文：[https://www.geeksforgeeks.org/intstream-builder-build-in-java/](https://www.geeksforgeeks.org/intstream-builder-build-in-java/)

`IntStream.Builder` 的 `build()` 方法用于构建流，将该构建器转换到*构建完成状态*。

**语法：**

```java
IntStream build()
```

**返回值：** 这个方法返回构建的流。

**注意：** 一个流构建器有一个生命周期，从*构建阶段*开始，在此期间可以添加元素，然后过渡到*构建完成阶段*，之后便不能再添加元素。构建阶段在调用 `build()` 方法时结束，该方法创建一个有序流，其元素是按照添加顺序添加到流构建器中的元素。

下面是举例说明 `build()` 方法的例子：

## 示例 1

```java
// Java code to show the implementation
// of IntStream.Builder build()

import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a Stream in building phase
        IntStream.Builder b = IntStream.builder();

        // Adding elements into the stream
        b.add(1);
        b.add(2);
        b.add(3);
        b.add(4);

        // Constructing the built stream using build()
        // This will enter the stream in built phase
        b.build().forEach(System.out::println);
    }
}
```

**输出：**

```java
1
2
3
4
```

## 示例 2

在调用 `build()` 方法后尝试在构建器中添加元素（当流已处于构建完成阶段时）。

```java
// Java code to show the implementation
// of IntStream.Builder build()

import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a Stream in building phase
        IntStream.Builder b = IntStream.builder();

        // Adding elements into the stream
        b.add(1);
        b.add(2);
        b.add(3);
        b.add(4);

        // Constructing the built stream using build()
        // This will enter the stream in built phase
        // Now no more elements can be added to this stream
        b.build().forEach(System.out::println);

        // Trying to add more elements in built phase
        // This will cause exception
        try {
            b.add(50);
        }
        catch (Exception e) {
            System.out.println("\nException: " + e);
        }
    }
}
```

**输出：**

```java
1
2
3
4

Exception: java.lang.IllegalStateException
```