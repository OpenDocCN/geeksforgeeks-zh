# Java 中的 IntStream 范围()

> 原文: [`https://www.geeksforgeeks.org/intstream-range-java/`](https://www.geeksforgeeks.org/intstream-range-java/)

`IntStream range(int startInclusive，int endExclusive)` 返回从 `startInclusive`(包含)到 `endExclusive`(排除)的顺序有序 `int` 流，增量步长为 1。

## 语法:

```java
static IntStream range(int startInclusive, int endExclusive)
```

## 参数:

*   `IntStream` : 一系列原始的 `int` 值元素。
*   `startInclusive` : 包含初始值。
*   `endExclusive` : 排除的上边界。

## 返回值:

`int` 元素范围的连续 `IntStream`。

## 示例:

```java
// Implementation of IntStream range
// (int startInclusive, int endExclusive)
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.range(6, 10);

        // Displaying the elements in range
        // including the lower bound but
        // excluding the upper bound
        stream.forEach(System.out::println);
    }
}
```

## Output:

```java

```

## 注意:

`int` 流 `range(int startInclusive，int endExclusive)` 基本上像 `for` 循环一样工作。递增值的等价序列可以按如下顺序产生:

```java
for (int i = startInclusive; i < endExclusive ; i++) 
{
 ...
 ...
 ...
}
```