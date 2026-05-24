# Ints.lastIndexOf() 函数 | 番石榴 | Java

> 原文：[https://www.geeksforgeeks.org/ints-lastindexof-function-guava-java/](https://www.geeksforgeeks.org/ints-lastindexof-function-guava-java/)

番石榴的 `Ints.lastIndexOf()` 返回数组中值 `target` 最后一次出现的索引。

## 语法

```java
public static int lastIndexOf(int[] array, int target)
```

## 参数

- **`array`**：一个 `int` 值的数组，可以为空。
- **`target`**：一个原始的 `int` 值。

## 返回值

`Ints.lastIndexOf()` 方法返回满足 `array[i] == target` 的最大索引 `i`，或者返回 `-1` 如果不存在这样的索引。

## 例 1

```java
// Java code to show implementation of
// Guava's Ints.lastIndexOf() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an integer array
        int[] arr = { 1, 2, 3, 4, 3, 5, 3, 4 };

        int target = 3;

        // Using Ints.lastIndexOf() method to get the
        // index of last appearance of a given element
        // in array and return -1 if element is
        // not found in the array
        int index = Ints.lastIndexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present at index "
                               + index);
        }
        else {
            System.out.println("Target is not present"
                               + " in the array");
        }
    }
}
```

### 输出

```java
Target is present at index 6
```

## 例 2

```java
// Java code to show implementation of
// Guava's Ints.lastIndexOf() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an integer array
        int[] arr = { 3, 5, 7, 11, 13 };

        int target = 17;

        // Using Ints.lastIndexOf() method to get the
        // index of last appearance of a given element
        // in array and return -1 if element is
        // not found in the array
        int index = Ints.lastIndexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present at index "
                               + index);
        }
        else {
            System.out.println("Target is not present"
                               + " in the array");
        }
    }
}
```

### 输出

```java
Target is not present in the array
```

## 参考

[https://google.github.io/guava/releases/22.0/api/docs/com/google/common/primitives/Ints.html#lastIndexOf-int:A-int-](https://google.github.io/guava/releases/22.0/api/docs/com/google/common/primitives/Ints.html#lastIndexOf-int:A-int-)