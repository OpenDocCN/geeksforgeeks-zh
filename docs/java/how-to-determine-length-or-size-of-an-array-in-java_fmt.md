# 如何在 Java 中确定数组的长度或大小？

> 原文：[https://www.geeksforgeeks.org/how-to-determine-length-or-size-of-an-array-in-java/](https://www.geeksforgeeks.org/how-to-determine-length-or-size-of-an-array-in-java/)

数组没有 `size()` 方法。但是在数组中有一个 `length` 字段可以用来查找数组的长度或大小。

`array.length`：`length` 是适用于数组的最终变量。借助 `length` 变量，我们可以得到数组的大小。

## 示例：

```java
int size = arr[].length;

// length can be used 
// for int[], double[], String[] 
// to know the length of the arrays.
```

下面是如何使用 `length` 变量获取 Java 中数组的长度的图示：

### 例 1：

```java
// Java program to illustrate
// how to get the length of the array

public class Test {
    public static void main(String[] args)
    {
        // Here array is the
        // array name of int type
        int[] array = new int[4];

        System.out.println("The size of "
                           + "the array is "
                           + array.length);
    }
}
```

**Output:**

```java
The size of the array is 4
```

### 例 2：

```java
// Java program to illustrate
// how to get the length of the array

public class Test {
    public static void main(String[] args)
    {
        // Here str is the array name
        // of String type.
        String[] str
            = { "GEEKS", "FOR", "GEEKS" };

        System.out.println("The size of "
                           + "the array is "
                           + str.length);
    }
}
```

**Output:**

```java
The size of the array is 3
```