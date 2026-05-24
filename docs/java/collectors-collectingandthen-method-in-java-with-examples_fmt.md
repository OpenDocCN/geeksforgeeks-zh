# 收集器收集 Java 中的 `collectingAndThen()` 方法示例

> 原文：[https://www.geeksforgeeks.org/collectors-collectingandthen-method-in-java-with-examples/](https://www.geeksforgeeks.org/collectors-collectingandthen-method-in-java-with-examples/)

Java 中 `Collector` 类的 `collectingAndThen(Collector downstream, Function finisher)` 方法，采用一个 `Collector`，这样我们就可以执行额外的整理转换。

## 语法

```java
public static <T, A, R, RR> 
       Collector<T, A, RR> 
       collectingAndThen(Collector<T, A, R> downstream, 
                         Function<R, RR> finisher)
```

其中：

*   `T`：输入元素的类型
*   `A`：下游收集器的中间堆积型
*   `R`：下游采集器的结果类型
*   `RR`：结果收集器的结果类型

## 参数

该方法接受下面列出的两个参数：

*   `downstream`：它是一个收集器的实例，也就是说我们可以在这里使用任何收集器。
*   `finisher`：它是一个函数的实例，该函数将应用于下游收集器的最终结果。

## 返回

返回一个 `Collector`，该收集器在 `finisher` 函数的帮助下，执行下游收集器的动作，然后是附加的整理步骤。

下面是一些例子来说明 `collectingAndThen` 的方法。

## 示例 1：创建不可变列表

```java
// Write Java code here
// Collectors collectingAndThen() method

import java.util.Collections;
import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.Stream;

public class GFG {
    public static void main(String[] args)
    {
        // Create an Immutable List
        List<String> lt
            = Stream
                  .of("GEEKS", "For", "GEEKS")
                  .collect(Collectors
                               .collectingAndThen(
                                   Collectors.toList(),
                                   Collections::<String> unmodifiableList));
        System.out.println(lt);
    }
}
```

**输出：**

```java
[GEEKS, For, GEEKS]
```

## 示例 2：创建不可变集合

```java
// Write Java code here
import java.util.Collections;
import java.util.List;
import java.util.Set;
import java.util.stream.Collectors;
import java.util.stream.Stream;

public class GFG {
    public static void main(String[] args)
    {
        // Create an Immutable Set
        Set<String> st
            = Stream
                  .of("GEEKS", "FOR", "GEEKS")
                  .collect(
                      Collectors
                          .collectingAndThen(Collectors.toSet(),
                                             Collections::<String>
                                                 unmodifiableSet));
        System.out.println(st);
    }
}
```

**输出：**

```java
[GEEKS, FOR]
```

## 示例 3：创建不可变映射

```java
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create an Immutable Map
        Map<String, String> mp
            = Stream
                  .of(new String[][] {
                      { "1", "Geeks" },
                      { "2", "For" },
                      { "3", "Geeks" } })
                  .collect(
                      Collectors
                          .collectingAndThen(
                              Collectors.toMap(p -> p[0], p -> p[1]),
                              Collections::<String, String>
                                  unmodifiableMap));
        System.out.println(mp);
    }
}
```

**输出：**

```java
{1=Geeks, 2=For, 3=Geeks}
```

**注意：** 这个方法最常用于创建不可变集合。