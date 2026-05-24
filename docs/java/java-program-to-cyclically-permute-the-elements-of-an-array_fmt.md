# 循环置换数组元素的 Java 程序

> 原文: [https://www.geeksforgeeks.org/java-program-to-cyclically-permute-the-elements-of-an-array/](https://www.geeksforgeeks.org/java-program-to-cyclically-permute-the-elements-of-an-array/)

给定一个整数数组，我们在那里循环置换它的元素，也就是说，将每个数组元素向左移动一个索引。第一个值将进入最后一个索引。

**例:**

```java
Input:    [1,2,3,4,5]
Output: [2,3,4,5,1]

Input:     [2,3,1,5,6]
Output:    [3,1,5,6,2]
```

## `方法#1`

1.  在函数 `cyclic shift()` 中，通过循环 `(i = 0; i < arr.length; i++)` 遍历数组并将每个元素移动一个位置。
2.  数组的第一个值在循环前存储在变量 `x` 中。
3.  最后，将数组的最后一个元素设置为 `x`。

### Java

```java
// Java Program to Cyclically Permute 
// the Elements of an Array
import java.util.*;
import java.io.*;

// function to print the array
class cycle {
    public int[] cycleShift(int[] arr)
    {
        int x = arr[0]; // store a[0]
        int i;
        for (i = 0; i < arr.length - 1; i++) {
            // for other element shift left
            arr[i] = arr[i + 1];
        }
        // for the last element in the modified array
        // it will be starting element
        arr[i] = x;
        return arr;
    }
}

public class GFG {
    public static void main(String[] args)
    {
        int[] arr = { 1, 2, 3, 4, 5 };
        cycle c = new cycle();
        int[] newArray = c.cycleShift(arr);
        for (int i = 0; i < newArray.length; i++) {
            System.out.print(newArray[i] + " ");
        }
    }
}
```

### 输出

```java
2 3 4 5 1
```