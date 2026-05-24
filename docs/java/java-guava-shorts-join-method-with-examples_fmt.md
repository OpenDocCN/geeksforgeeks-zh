# Java 番石榴 Shorts.join() 方法带示例

> 原文：[https://www.geeksforgeeks.org/java-guava-shorts-join-method-with-examples/](https://www.geeksforgeeks.org/java-guava-shorts-join-method-with-examples/)

`Shorts.join()` 是番石榴库中 [`Shorts`](https://www.geeksforgeeks.org/shorts-class-guava-java/) 类的一种方法，它返回由分隔符分隔的所有给定短值的组合字符串。例如，`join("-", (short) 1, (short) 2, (short) 3)` 返回字符串 `"1-2-3"`。

## 语法

```java
public static String join(String separator,
                          short... array)
```

## 参数

*   `separator`：应出现在结果字符串中连续值之间的文本（但不在开头或结尾）。
*   `array`：一个短值数组，可以为空。

## 返回值

包含由 `separator` 分隔的短值的字符串。

## 示例-1

```java
// Java code to show implementation of
// Guava's Shorts.join() method
import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating a short array
        short[] arr = { 2, 4, 6, 8, 10 };

        // Using Shorts.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Shorts.join("#", arr));
    }
}
```

**输出：**

```java
2#4#6#8#10
```

## 示例-2

```java
// Java code to show implementation of
// Guava's Shorts.join() method
import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating a short array
        short[] arr = { 3, 5, 7, 9, 11 };

        // Using Shorts.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Shorts.join("*", arr));
    }
}
```

**输出：**

```java
3*5*7*9*11
```

## 参考

[https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#join-java.lang.String-short...-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#join-java.lang.String-short...-)