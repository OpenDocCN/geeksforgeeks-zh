# Java 中的 Collectors groupingBy()方法，示例

> 原文:[https://www . geesforgeks . org/collectors-group ingby-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collectors-groupingby-method-in-java-with-examples/)

Java 中 `Collectors` 类的 `groupingBy()` 方法用于根据某些属性对对象进行分组，并将结果存储在 `Map` 实例中。为了使用它，我们总是需要指定一个属性来执行分组。该方法提供了与 SQL 的 `GROUP BY` 子句相似的功能。

**语法:**

> `public static <T, K> Collector<T, ?, Map<K, List<T>>> groupingBy(Function<? super T, ? extends K> classifier)`

**类型参数:** 该方法取两个类型参数:

*   `T` - 是输入元素的类型。
*   `K` - 是输入元素要转换的类型。

**参数:** 该方法接受两个强制参数:

*   `classifier` - 它是要应用于输入元素的属性。
*   `downstream` - 用于将输入元素映射到目的地图中。

**返回值:** 以地图形式返回一个采集器。

下面是 `groupingBy()` 方法的程序实现:

### 代码示例

```java
// Java program to demonstrate
// Collectors groupingBy() method

import java.util.*;
import java.util.function.Function;
import java.util.stream.Collectors;

public class GFG {
    public static void main(String[] args)
    {

        // Get the List
        List<String> g
            = Arrays.asList("geeks", "for", "geeks");

        // Collect the list as map
        // by groupingBy() method
        Map<String, Long> result
            = g.stream().collect(
                Collectors.groupingBy(
                    Function.identity(),
                    Collectors.counting()));

        // Print the result
        System.out.println(result);
    }
}
```

**输出:**

```java
{geeks=2, for=1}
```

**参考:** [https://docs.oracle.com/javase/8/docs/api/java/util/stream/Collectors.html#groupingBy-java.util.function.Function-](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Collectors.html#groupingBy-java.util.function.Function-)