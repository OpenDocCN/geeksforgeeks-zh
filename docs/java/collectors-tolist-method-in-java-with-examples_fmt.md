# Java 中的收集器 toList()方法，示例

> 原文：[https://www.geeksforgeeks.org/collectors-tolist-method-in-java-with-examples/](https://www.geeksforgeeks.org/collectors-tolist-method-in-java-with-examples/)

`Collectors`类的`toList()`方法是一种静态方法。它返回一个`Collector`接口，将输入数据收集到一个新列表中。此方法从不保证返回列表的类型、可变性、可序列化性或线程安全性，但是为了更好地控制，可以使用`Collection(Supplier)`方法。这是一个未排序的收集器。

**语法：**

```java
public static <T> Collector<T, ?, List<T>> toList()
```

其中：

*   `T`：输入元素的类型。
*   接口`Collector<T, A, R>`：将输入元素累积到可变结果容器中的可变约简操作，可选地在所有输入元素都被处理后将累积的结果转换为最终表示。还原操作可以顺序执行，也可以并行执行。
    *   `T`：归约运算的输入元素类型。
    *   `A`：还原操作的可变累加类型。
    *   `R`：归约运算的结果类型。
*   `toList()`：`Collectors`类的静态方法，返回一个`Collector`接口对象，用于将一组数据存储到列表中。`Collectors`类在`java.util.stream`包下。

**返回值：** 这个方法返回一个`Collector`，它按照遇到的顺序将所有的输入元素收集到一个列表中。

下面是用 Java 说明`toList()`方法的例子：

**例 1：**

```java
// Java code to show the implementation of
// Collectors toList() function

import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a Stream of strings
        Stream<String> s = Stream.of("Geeks",
                                     "for",
                                     "GeeksforGeeks",
                                     "Geeks Classes");

        // using Collectors toList() function
        List<String> myList = s.collect(Collectors.toList());

        // printing the elements
        System.out.println(myList);
    }
}
```

**Output：**

```java
[Geeks, for, GeeksforGeeks, Geeks Classes]
```

**例 2：**

```java
// Java code to show the implementation of
// Collectors toList() function

import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a Stream of strings
        Stream<String> s = Stream.of("1", "2", "3", "4");

        // using Collectors toList() function
        List<String> myList = s.collect(Collectors.toList());

        // printing the elements
        System.out.println(myList);
    }
}
```

**Output：**

```java
[1, 2, 3, 4]
```