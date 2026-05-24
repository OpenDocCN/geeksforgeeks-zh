# LongStream.Builder build() in Java

> 原文: [https://www.geeksforgeeks.org/longstream-builder-build-in-java/](https://www.geeksforgeeks.org/longstream-builder-build-in-java/)

`LongStream.Builder` 的 `build()` 方法用于构建一个流，将该构建器转换到*构建完成状态*。

**语法:**

```java
LongStream build()
```

**返回值:** 这个方法返回构建的流。

**注意:** 一个流构建器有一个生命周期，从*构建阶段*开始，在此期间可以添加元素，然后过渡到*构建完成阶段*，之后便不能再添加元素。构建阶段在调用 `build()` 方法时结束，该方法创建一个有序流，其元素是按照添加顺序添加到流构建器中的元素。

下面是举例说明 `build()` 方法的例子:

**例 1:**

```java
// Java code to show the implementation
// of LongStream.Builder build()

import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a Stream in building phase
        LongStream.Builder b = LongStream.builder();

        // Adding elements into the stream
        b.add(1L);
        b.add(2L);
        b.add(3L);
        b.add(4L);

        // Constructing the built stream using build()
        // This will enter the stream in built phase
        b.build().forEach(System.out::println);
    }
}
```

**Output:**

```java

```

**示例 2:** 在调用 `build()` 方法后尝试在流中添加元素（当流处于构建完成阶段时）。

```java
// Java code to show the implementation
// of LongStream.Builder build()

import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a Stream in building phase
        LongStream.Builder b = LongStream.builder();

        // Adding elements into the stream
        b.add(1L);
        b.add(2L);
        b.add(3L);
        b.add(4L);

        // Constructing the built stream using build()
        // This will enter the stream in built phase
        // Now no more elements can be added to this stream
        b.build().forEach(System.out::println);

        // Trying to add more elements in built phase
        // This will cause exception
        try {
            b.add(50L);
        }
        catch (Exception e) {
            System.out.println("\nException: " + e);
        }
    }
}
```

**Output:**

```java

```

**输出:**

```java
Exception: java.lang.IllegalStateException
```