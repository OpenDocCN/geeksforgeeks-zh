# Java 中的 IntStream anyMatch()，示例

> 原文：[https://www.geeksforgeeks.org/intstream-anymatch-java-examples/](https://www.geeksforgeeks.org/intstream-anymatch-java-examples/)

`IntStream anyMatch(IntPredicate predicate)`返回此流的任何**元素是否与提供的谓词匹配。如果不是确定结果所必需的，它可能不会计算所有元素上的谓词。这是一次**短路端子操作。**如果终端操作在无限输入时可能在有限时间内终止，则该操作为短路。

## 语法

```java
boolean anyMatch(IntPredicate predicate)
```

其中，`IntPredicate`表示一个谓词（布尔值函数），接受一个`int`类型的参数。如果流中有任何元素与提供的谓词匹配，则函数返回`true`，否则返回`false`。

**注意：**如果流为空，则返回`false`，不计算谓词。

## 示例 1

`anyMatch()`函数检查列表中的任何元素是否满足给定条件。

```java
// Java code for IntStream anyMatch
// (Predicate predicate) to check whether
// any element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(1, 2, 3, 4, 5, 6);

        // Stream anyMatch(Predicate predicate)
        boolean answer = stream.anyMatch(num -> (num - 5) > 0);

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出：

```java
true
```

## 示例 2

`anyMatch()`函数检查流中任意元素的平方根是否大于 8。

```java
// Java code for IntStream anyMatch
// (Predicate predicate) to check whether
// any element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(10, 20, 30, 40, 50);

        // Stream anyMatch(Predicate predicate)
        boolean answer = stream.anyMatch(num -> Math.sqrt(num) > 8);

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出：

```java
false
```

## 示例 3

`anyMatch()`函数显示如果流为空，则返回`false`。

```java
// Java code for IntStream anyMatch
// (Predicate predicate) to check whether
// any element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an empty IntStream
        IntStream stream = IntStream.empty();

        boolean answer = stream.anyMatch(num -> true);

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出：

```java
false
```