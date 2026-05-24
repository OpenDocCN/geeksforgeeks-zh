# Shorts.asList() 方法详解（带示例）

> 原文：[https://www.geeksforgeeks.org/java-guava-shorts-aslist-method-with-examples/](https://www.geeksforgeeks.org/java-guava-shorts-aslist-method-with-examples/)

## 方法介绍

番石榴 [`Shorts`](https://www.geeksforgeeks.org/shorts-class-guava-java/) 类的 `Shorts.asList()` 方法接受一个 `short` 数组作为参数，返回一个有固定大小的列表。返回的列表由作为参数传递的 `short` 数组支持。这意味着在作为参数传递的数组中所做的更改将反映在方法返回的列表中，反之亦然。

## 语法

```java
public static List<Short> asList(short… backingArray)
```

## 参数

该方法接受一个强制参数 `backingArray`，这是一个用于支持列表的 `short` 数组。

## 返回值

该方法返回一个固定大小的列表，该列表由作为参数传递给方法的数组支持。换句话说，该方法返回数组的列表视图。

下面的例子说明了上述方法的实现：

## 示例

### 例 1

```java
// Java code to show implementation of
// Guava's Shorts.asList() method

import com.google.common.primitives.Shorts;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a Short array
        short arr[] = { 1, 2, 3, 4, 5 };

        // Using Shorts.asList() method to wrap
        // the specified primitive Short array
        // as a List of the Short type
        List<Short> myList = Shorts.asList(arr);

        // Displaying the elements in List
        System.out.println(myList);
    }
}
```

**输出：**

```java
[1, 2, 3, 4, 5]
```

### 例 2

```java
// Java code to show implementation of
// Guava's Shorts.asList() method

import com.google.common.primitives.Shorts;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a Short array
        short arr[] = { 3, 5, 7 };

        // Using Shorts.asList() method to wrap
        // the specified primitive Short array
        // as a List of the Short type
        List<Short> myList = Shorts.asList(arr);

        // Displaying the elements in List
        System.out.println(myList);
    }
}
```

**输出：**

```java
[3, 5, 7]
```

## 参考

[https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#asList-short...-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#asList-short...-)