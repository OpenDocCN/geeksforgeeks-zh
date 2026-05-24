# 检查给定的数是否可以表示为两个大数之和

> 原文：[https://www.geeksforgeeks.org/check-given-number-can-represented-sum-two-great-numbers/](https://www.geeksforgeeks.org/check-given-number-can-represented-sum-two-great-numbers/)

## 问题描述

给我们一个数字 `N`，我们需要检查给定的数字 `N` 是否可以表示为两个“大”数的和。如果是，则打印这两个大数字，否则打印 `No`。大数字是以下列形式表示的数字：`((b)*(b+1)*(2*b+1))/6`，其中 `b` 是自然数。

## 示例

```
Input  : N = 35
Output : 5 and 30

Input  : 105
Output : 14 and 91

Input : 99
Output : No the given number is not 
a sum of two great numbers
```

## 算法思路

正如我们所知，`((b)*(b+1)*(2*b+1))/6` 其中 `b` 是自然数，表示前 `b` 个自然数的平方和。例如，如果 `b = 3`，那么 `1+4+9 = 14`。

因此，为了检查输入数 `n` 是否可以表示为两个大数之和，我们将首先计算数组中小于 `n` 的所有大数。然后，我们将使用两个指针的方法来找到可以加起来等于给定数字 `n` 的对。

为了计算所有大数的数组，我们将迭代 `i=0` 到 `i < n`，然后在一个变量 `temp` 中，我们将在每次迭代的最后添加 `i` 并存储它。使用双指针方法检查给定的数组是否包含和为 `n` 的数对，打印它们，否则打印 `No`。

## Java 实现

```java
import java.util.ArrayList;
class GreatNumberSum {
    // O(N) 时间 | O(N) 辅助空间
    public static void greatNumberComputation(int n) {
        // 预计算所有小于 n 的大数
        ArrayList<Integer> arr = new ArrayList<>();
        // 从 1 开始遍历
        for (int i = 1; i < n; i++) {
            // 计算当前大数
            int square = (i * (i + 1) * (2 * i + 1)) / 6;
            if (square > n) {
                break;
            }
            arr.add(square);
        }
        countPairs(arr, n);
    }
    static void countPairs(ArrayList<Integer> arr, int target) {
        // 数组已经排序，所以可以使用双指针
        int lo = 0, hi = arr.size() - 1;
        boolean found = false;
        while (lo < hi) {
            int currentSum = arr.get(lo) + arr.get(hi);
            if (currentSum == target) {
                System.out.println(arr.get(lo) + " and " + arr.get(hi));
                found = true;
                hi--;
                lo++;
            } else if (currentSum < target) {
                lo++;
            } else {
                hi--;
            }
        }
        if (!found) {
            System.out.println("No the given number is not a sum of two great numbers");
        }
    }
    // 驱动代码
    public static void main(String[] args) {
        int n = 105;
        greatNumberComputation(n);
    }
}
```

输出：
```
14 and 91
```

## 复杂度分析

- 时间复杂度：`O(N)`
- 辅助空间：`O(N)`

## 贡献信息

本文由 [**Sanket Singh 2**](https://auth.geeksforgeeks.org/profile.php?user=Sanket Singh 2) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息。