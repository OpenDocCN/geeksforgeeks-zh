# 使用 Java 中的位集从整数数组中查找缺失的数字

> 原文：[https://www.geeksforgeeks.org/finding-missing-number-from-integer-array-using-bitset-in-java/](https://www.geeksforgeeks.org/finding-missing-number-from-integer-array-using-bitset-in-java/)

给定一个从 1 到 n 的整数数组，要求您从数组中找到缺少的数字。

## 例：

```java
Input : n = 5, a[] = {1, 2, 4, 5}
Output: 3
Explanation: From the array of numbers 1 to 5, 3 is missing.

Input : n = 10, a[] = {1, 3, 4, 6, 8, 10}
Output: 2, 5, 7, 9
Explanation: From the array of numbers 1 to 10, 2, 5, 7 and 9 are missing.
```

这个问题很容易解决，通过计算 n 个数的和，用公式，

```java
sum = (n * (n + 1)) / 2
```

在[这篇](https://www.geeksforgeeks.org/find-the-missing-number/)文章中给出了这种方法的解决方案。

但是，该方法不能用于数组包含多个缺失数字的情况。

对于这种情况，Java 中的 `BitSet` 实用程序类可以用来解决这个问题。

## 方法：

1.  找出给定数组中缺失元素的数量，记为 `misscnt`。
2.  创建一个以 `n` 为参数的 `BitSet` 类对象。
3.  对于给定数组中的每个数字，使用 `bitset.set()` 方法将其对应的位设置为 `true`。
4.  初始化一个整型变量 `lastMissIndex`，用于存储上一个缺失元素的索引。
5.  使用从 0 到 `misscnt` 的循环，利用 `bitset.nextClearBit()` 方法，从 `lastMissIndex` 开始查找第一个设置为 `false` 的位。
6.  将 `lastMissIndex` 加 1，然后输出。

下面是上述方法的实现

## Java

```java
// Java Program to find the missing elements
// from integer array using BitSet class

import java.io.*;
import java.util.*;

public class FindMissingNo {
    private static void findMissingNumbers(int arr[], int n)
    {
        int missCnt = n - arr.length;
        // create Bitset object b
        BitSet b = new BitSet(n);
        for (int i : arr) {
            b.set(i - 1);
        }
        int lastMissIndex = 0;
        for (int i = 0; i < missCnt; ++i) {
            lastMissIndex = b.nextClearBit(lastMissIndex);
            // print missing number
            System.out.println(++lastMissIndex);
        }
    }
    public static void main(String[] args)
    {
        int n = 10;
        // array of 10 numbers
        int[] arr = new int[] { 1, 2, 4, 6, 8, 9 };
        // call function
        findMissingNumbers(arr, n);
    }
}
```

## 输出

```
3
5
7
10
```

本文由 **Nithiyashree M G** 供稿。