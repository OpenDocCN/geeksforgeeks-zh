# 如何在 Java 8 中打印一个流的元素

> 原文：[https://www.geeksforgeeks.org/how-to-print-elements-of-a-stream-in-java-8/](https://www.geeksforgeeks.org/how-to-print-elements-of-a-stream-in-java-8/)

在 Java 8 中引入[流应用编程接口](https://www.geeksforgeeks.org/stream-in-java/)用于处理对象的集合。流是支持各种方法的对象序列，这些方法可以通过流水线来产生所需的结果。
Java流的特点是–

*   流不是数据结构，而是从集合、数组或输入/输出通道获取输入。
*   流不改变原始的数据结构，它们只根据流水线方法提供结果。
*   每个中间操作都被延迟执行，并作为结果返回一个流，因此各种中间操作可以被流水线化。终端操作标记流的结尾并返回结果。

用 Java 打印流的元素有 3 种方法:

1.  `forEach()`
2.  `println()`和`collect()`
3.  `peek()`

以下是详细打印流的三种方法:

## 1. `Stream.forEach(Consumer action)`

此方法对流的每个元素执行一个操作。`Stream.forEach(Consumer action)`是一个**终端操作**，即它可能遍历流以产生结果或副作用。

### 语法

```java
void forEach(Consumer<? super T> action)
```

其中，`Consumer`是一个函数式接口，`T`是流元素的类型。

下面是如何使用`forEach()`方法打印`Stream`的元素:

### 程序 1

```java
// Java code to print the elements of Stream
import java.util.stream.*;

class GFG {
    public static void main(String[] args)
    {
        // Get the stream
        Stream<String> stream = Stream.of("Geeks", "For",
                                          "Geeks", "A",
                                          "Computer", "Portal");

        // Print the stream
        stream.forEach(s -> System.out.println(s));
    }
}
```

### 输出

```java
Geeks
For
Geeks
A
Computer
Portal
```

### 程序 2

使用短手λ表达式

```java
// Java code to print the elements of Stream
import java.util.stream.*;

class GFG {
    public static void main(String[] args)
    {
        // Get the stream
        Stream<String> stream = Stream.of("Geeks", "For",
                                          "Geeks", "A",
                                          "Computer", "Portal");

        // Print the stream
        stream.forEach(System.out::println);
    }
}
```

### 输出

```java
Geeks
For
Geeks
A
Computer
Portal
```

### 程序 3

这种方法消耗流，并使其不可用于将来的使用。因此，下面的代码将抛出一个错误，因为流已经被使用了。

```java
// Java code to print the elements of Stream
import java.util.stream.*;

class GFG {
    public static void main(String[] args)
    {
        // Get the stream
        Stream<String> stream = Stream.of("Geeks", "For",
                                          "Geeks", "A",
                                          "Computer", "Portal");

        // Print the stream
        stream.forEach(s -> System.out.println(s));

        // Since the stream has been already consumed
        // this will throw exception
        try {
            // Print the stream
            stream.forEach(s -> System.out.println(s));
        }
        catch (Exception e) {
            System.out.println("\nException: " + e);
        }
    }
}
```

### 输出

```java
Geeks
For
Geeks
A
Computer
Portal

Exception: java.lang.IllegalStateException: 
stream has already been operated upon or closed
```

## 2. 使用`println()`与`collect()`

此方法将流的元素收集为一个收集器实例，例如`List`。因此，可以使用`println()`方法轻松打印`List`。

### 语法

```java
System.out.println(stream.collect(Collectors.toList()));
```

### 程序 1

```java
// Java code to print the elements of Stream
import java.util.stream.*;

class GFG {
    public static void main(String[] args)
    {
        // Get the stream
        Stream<String> stream = Stream.of("Geeks", "For",
                                          "Geeks", "A",
                                          "Computer", "Portal");

        // Print the stream
        System.out.println(stream.collect(Collectors.toList()));
    }
}
```

### 输出

```java
[Geeks, For, Geeks, A, Computer, Portal]
```

### 程序 2

这种方法也会消耗该流，并使其不可用于未来使用。因此，下面的代码将抛出一个错误，因为流已经被使用了。

```java
// Java code to print the elements of Stream
import java.util.stream.*;

class GFG {
    public static void main(String[] args)
    {
        // Get the stream
        Stream<String> stream = Stream.of("Geeks", "For",
                                          "Geeks", "A",
                                          "Computer", "Portal");

        // Print the stream
        System.out.println(stream.collect(Collectors.toList()));

        // Since the stream has been already consumed
        // this will throw exception
        try {
            // Print the stream
            System.out.println(stream.collect(Collectors.toList()));
        }
        catch (Exception e) {
            System.out.println("\nException: " + e);
        }
    }
}
```

### 输出

```java
[Geeks, For, Geeks, A, Computer, Portal]

Exception: java.lang.IllegalStateException: 
stream has already been operated upon or closed
```

## 3. `Stream.peek(Consumer action)`

此方法返回一个由该流的元素组成的流，另外在从结果流中消费元素时对每个元素执行提供的操作。这是一个**中间操作**，即它创建一个新的流，当遍历时，包含与给定谓词匹配的初始流的元素。

### 语法

```java
Stream<T> peek(Consumer<? super T> action)
```

其中，`Stream`是一个接口，`T`是流元素的类型。`action`是一个在元素从流中消费时对其执行的非干扰操作，该函数返回新流。

### 程序 1

```java
// Java code to print the elements of Stream
import java.util.stream.*;

class GFG {
    public static void main(String[] args)
    {
        // Get the stream
        Stream<String> stream = Stream.of("Geeks", "For",
                                          "Geeks", "A",
                                          "Computer", "Portal");

        // Print the stream using peek()
        // by providing a terminal operation count()
        stream.peek(s -> System.out.println(s)).count();
    }
}
```

### 输出

```java
Geeks
For
Geeks
A
Computer
Portal
```

### 程序 2

这个方法**不消耗**流。因此下面的代码不会抛出任何错误。

```java
// Java code to print the elements of Stream
import java.util.stream.*;

class GFG {
    public static void main(String[] args)
    {
        // Get the stream
        Stream<String> stream = Stream.of("Geeks", "For",
                                          "GeeksForGeeks", "A",
                                          "Computer", "Portal");

        // Since the stream is not being consumed
        // this will not throw any exception

        // Print the stream
        stream.filter(s -> s.startsWith("G"))
            .peek(s -> System.out.println("Filtered value: " + s))
            .map(String::toUpperCase)
            .peek(s -> System.out.println("Uppercase value :" + s))
            .count();
    }
}
```

### 输出

```java
Filtered value: Geeks
Uppercase value :GEEKS
Filtered value: GeeksForGeeks
Uppercase value :GEEKSFORGEEKS
```