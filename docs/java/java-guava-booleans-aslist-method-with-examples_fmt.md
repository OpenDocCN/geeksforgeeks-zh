# Java 番石榴 | `Booleans.asList()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/java-guava-booleans-aslist-method-with-examples/](https://www.geeksforgeeks.org/java-guava-booleans-aslist-method-with-examples/)

番石榴的 [`Booleans`](https://www.geeksforgeeks.org/booleans-class-guava-java/) 类的 `Booleans.asList()` 方法接受一个布尔数组作为参数，并返回一个固定大小的列表。返回的列表由作为参数传递的布尔数组支持。这意味着在作为参数传递的数组中所做的更改将反映在方法返回的列表中，反之亦然。

## 语法

```java
public static List<Boolean> asList(boolean... backingArray)
```

## 参数

该方法接受一个强制参数 `backingArray`，这是一个用于支持列表的布尔数组。

## 返回值

方法 `Booleans.asList()` 返回一个固定大小的列表，该列表由作为参数传递给方法的数组支持。换句话说，该方法返回数组的列表视图。

下面的例子说明了上述方法的实现：

## 例 1

```java
// Java code to show implementation of
// Guava's Booleans.asList() method

import com.google.common.primitives.Booleans;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Boolean array
        boolean arr[] = { true, false, true,
                          true, true };

        // Using Booleans.asList() method to wrap
        // the specified primitive Boolean array
        // as a List of the Boolean type
        List<Boolean> myList = Booleans.asList(arr);

        // Displaying the elements in List
        System.out.println(myList);
    }
}
```

**输出：**

```java
[true, false, true, true, true]
```

## 例 2

```java
// Java code to show implementation of
// Guava's Booleans.asList() method

import com.google.common.primitives.Booleans;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Boolean array
        boolean arr[] = { false, true, false };

        // Using Booleans.asList() method to wrap
        // the specified primitive Boolean array
        // as a List of the Boolean type
        List<Boolean> myList = Booleans.asList(arr);

        // Displaying the elements in List
        System.out.println(myList);
    }
}
```

**输出：**

```java
[false, true, false]
```

## 参考

[https://google.github.io/guava/releases/20.0/api/docs/com/google/common/primitives/Booleans.html#asList-boolean...-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/primitives/Booleans.html#asList-boolean...-)