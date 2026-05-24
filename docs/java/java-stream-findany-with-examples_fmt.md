# Java Stream findAny() 带示例

> 原文: [https://www.geeksforgeeks.org/java-stream-findany-with-examples/](https://www.geeksforgeeks.org/java-stream-findany-with-examples/)

`Stream findAny()` 返回一个描述流的某个元素的 `Optional` 对象（可以包含也可以不包含非空值的容器对象），如果流为空，则返回一个空的 `Optional` 对象。

## findAny() 与 findFirst() 的比较

`findAny()` 方法从流中返回任何元素，但是可能会有这样的情况，我们需要提取过滤流的第一个元素。当正在处理的流具有定义的相遇顺序（流的元素被处理的顺序）时，那么 [`findFirst()`](https://www.geeksforgeeks.org/stream-findfirst-java-examples/) 是有用的，它返回流中的第一个元素。

## 语法

```java
Optional<T> findAny()
```

其中，`Optional` 是一个容器对象，它可能或可能不包含一个非空值，`T` 是对象的类型。该函数返回一个描述此流中某个元素的 `Optional`，如果流为空则返回一个空的 `Optional`。

## 异常

如果选择的元素为空，则抛出 `NullPointerException`。

## 注意

`findAny()` 是 `Stream` 接口的一个 **端子-短路** 操作。此方法返回满足中间操作的任何第一个元素。这是一个短路操作，因为它只需要返回 **'any'** 第一个元素，并终止剩余的迭代。

## 示例 1：整数流上的 findAny() 方法

```java
// Java code for Stream findAny()
// which returns an Optional describing
// some element of the stream, or an
// empty Optional if the stream is empty.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a List of Integers
        List<Integer> list = Arrays.asList(2, 4, 6, 8, 10);

        // Using Stream findAny() to return
        // an Optional describing some element
        // of the stream
        Optional<Integer> answer = list.stream().findAny();

        // if the stream is empty, an empty
        // Optional is returned.
        if (answer.isPresent()) {
            System.out.println(answer.get());
        }
        else {
            System.out.println("no value");
        }
    }
}
```

输出:

```java

```

## 示例 2：字符串流上的 findAny() 函数

```java
// Java code for Stream findAny()
// which returns an Optional describing
// some element of the stream, or an
// empty Optional if the stream is empty.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a List of Strings
        List<String> list = Arrays.asList("Geeks", "for",
                                          "GeeksQuiz", "GFG");

        // Using Stream findAny() to return
        // an Optional describing some element
        // of the stream
        Optional<String> answer = list.stream().findAny();

        // if the stream is empty, an empty
        // Optional is returned.
        if (answer.isPresent()) {
            System.out.println(answer.get());
        }
        else {
            System.out.println("no value");
        }
    }
}
```

输出:

```java
Geeks
```

## 注意

`Stream findAny()` 操作的行为是显式的 **非确定性的**，即可以自由选择流中的任意元素。对同一源的多次调用可能不会返回相同的结果。

## 示例 3：findAny() 方法以非确定性方式返回可被 4 整除的元素

```java
// Java code for Stream findAny()
// which returns an Optional describing
// some element of the stream, or an
// empty Optional if the stream is empty.
import java.util.OptionalInt;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args) {

        // Creating an IntStream
        IntStream stream = IntStream.of(4, 5, 8, 10, 12, 16)
                           .parallel();

        // Using Stream findAny().
        // Executing the source code multiple times
        // may not return the same result.
        // Every time you may get a different
        // Integer which is divisible by 4.
        stream = stream.filter(i -> i % 4 == 0);

        OptionalInt answer = stream.findAny();
        if (answer.isPresent())
        {
            System.out.println(answer.getAsInt());
        }
    }
}
```

输出:

```java

```