# Ints indexOf()函数 | 番石榴 | Java

> 原文: [https://www.geeksforgeeks.org/ints-indexof-function-guava-java/](https://www.geeksforgeeks.org/ints-indexof-function-guava-java/)

番石榴的 `Ints.indexOf(int[] array, int target)` 方法返回数组中值 `target` 的第一个出现的索引。

## 语法:
```java
public static int indexOf(int[] array, int target)
```

## 参数:
此方法接受以下参数:
* `array`: 一个 `int` 值的数组，可能为空。
* `target`: 一个原始的 `int` 值。

## 返回值:
此方法返回最小索引 `i` 使得 `array[i] == target`，或者 `-1` 如果不存在这样的索引。

## 例 1:
```java
// Java code to show implementation of
// Guava's Ints.indexOf() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating an integer array
        int[] arr = { 1, 2, 3, 4, 3, 5 };
        int target = 3;

        // Using Ints.indexOf(int[] array, int target)
        // method to get the index of first appearance
        // of a given element in array and return -1
        // if element is not found in the array
        int index = Ints.indexOf(arr, target);

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

## 输出:
```java
Target is present at index 2
```

## 例 2:
```java
// Java code to show implementation of
// Guava's Ints.indexOf() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating an integer array
        int[] arr = { 3, 5, 7, 11, 13 };
        int target = 17;

        // Using Ints.indexOf(int[] array, int target) method
        // to get the index of first appearance of a
        // given element in array and return -1 if
        // element is not found in the array
        int index = Ints.indexOf(arr, target);

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

## 输出:
```java
Target is not present in the array
```

## 参考:
[https://google.github.io/guava/releases/22.0/api/docs/com/google/common/primitives/Ints.html#indexOf-int:A-int-](https://google.github.io/guava/releases/22.0/api/docs/com/google/common/primitives/Ints.html#indexOf-int:A-int-)