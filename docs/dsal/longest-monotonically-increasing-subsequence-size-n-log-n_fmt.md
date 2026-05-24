# 最长递增子序列大小（`N log N`）

> 原文： [https://www.geeksforgeeks.org/longest-monotonically-increasing-subsequence-size-n-log-n/](https://www.geeksforgeeks.org/longest-monotonically-increasing-subsequence-size-n-log-n/)

给定一个随机数数组。 在数组中找到最长的[递增子序列](http://en.wikipedia.org/wiki/Substring)（LIS）。 我知道你们中许多人可能已经阅读[递归和动态规划](https://www.geeksforgeeks.org/longest-increasing-subsequence-dp-3/)（DP）解决方案。 论坛帖子中很少有人要求[`O(N log N)`](http://en.wikipedia.org/wiki/Longest_increasing_subsequence#Efficient_algorithms)算法。

暂时，无需考虑递归和 DP 解决方案。 让我们抽取少量样本并将解决方案扩展到大型实例。 尽管乍一看可能很复杂，但是一旦我们理解了逻辑，编码就很简单。

## 算法策略

考虑输入数组`A = {2, 5, 3}`。 我将在解释过程中扩展数组。

通过观察，我们知道 LIS 是`{2, 3}`或`{2, 5}`。 **请注意，我仅考虑严格增加的序列**。

让我们再添加两个元素，例如 7、11。 这些元素将扩展现有序列。 现在，输入数组`{2, 5, 3, 7, 11}`的递增序列为`{2, 3, 7, 11}`和`{2, 5, 7, 11}`。

此外，我们在数组中再添加一个元素，例如 8，即输入数组变为`{2, 5, 3, 7, 11, 8}`。 请注意，最新元素 8 大于任何活动序列的最小元素（**将简短讨论活动序列**）。 如何将现有序列扩展为 8？ 首先，8 可以成为 LIS 的一部分吗？ 如果是，怎么办？ 如果我们要添加 8，它应该在 7 之后（通过替换 11）。

由于此方法是**离线的**（我们的意思是[离线](https://www.geeksforgeeks.org/median-of-stream-of-integers-running-integers/)吗？），因此我们不确定是否添加 8 将扩展该系列。 假设输入数组中有 9 个，例如`{2, 5, 3, 7, 11, 8, 7, 9, …}`。 我们可以将 8 替换为 11，因为可能存在**最佳**候选（9），可以扩展新系列`{2, 3, 7, 8}`或`{2, 5, 7, 8}`。

我们的观察结果是，假设最大序列的结尾元素为`E`。如果存在元素`A[j] (j > i)`，我们可以向现有序列中添加（替换）当前元素`E < A[i] < A[j]`或（`E > A[i] < A[j]` – 用于替换）。 在上面的示例中，`E = 11`，`A[i] = 8`，`A[j] = 9`。

对于原始数组`{2, 5, 3}`，请注意，当我们将 3 添加到递增序列`{2, 5}`时，我们会遇到相同的情况。 我只是创建了两个递增的序列，以使说明变得简单。 3 可以代替序列`{2, 5}`中的 5，而不是两个序列。

我知道这会令人困惑，我会尽快清除它！

**问题是，什么时候可以安全地添加或替换现有序列中的元素？**

让我们考虑另一个样本`A = {2, 5, 3}`。 假设下一个元素是 1。如何扩展当前序列`{2, 3}`或`{2, 5}`。 显然，它也不能扩展。 但是，新的最小元素有可能成为 LIS 的开始。 为了清楚起见，请考虑数组为`{2, 5, 3, 1, 2, 3, 4, 5, 6}`。 将 1 设为新序列将创建最大的新序列。

**观察结果是，当我们遇到数组中的新最小元素时，它可能是开始新序列的潜在候选者。**

从观察中，我们需要维护递增序列的列表。

总的来说，我们有一组**活动列表**不同长度。 我们将元素`A[i]`添加到这些列表中。 我们以长度减少的顺序扫描列表（用于结束元素）。 我们将验证所有列表的末端元素，以找到一个末端元素小于`A[i]`（**下限**值）的列表。

我们的策略由以下条件决定，

```
1. If A[i] is smallest among all *end* 
   candidates of active lists, we will *start* 
   new active list of length 1.
```

```
2. If A[i] is largest among all *end* candidates of 
  active lists, we will clone the *largest* active 
  list, and extend it by A[i].
```

```
 3. If A[i] is in between, we will find a list with 
  *largest end element that is smaller than* A[i]. 
  Clone and extend this list by A[i]. We will discard all
  other lists of same length as that of this modified list.
```

请注意，在构造活动列表的任何时候，都将保持以下条件。

**“较小列表的末尾元素小于较大列表的末尾元素”**。

## 详细示例

举一个很明显的例子，使用 [Wiki](http://en.wikipedia.org/wiki/Longest_increasing_subsequence) `{0, 8, 4, 12, 2, 10, 6, 14, 1, 9, 5, 13, 13, 3, 11, 7, 15}`。

```
A[0] = 0. Case 1. There are no active lists, create one.
0.

A[1] = 8. Case 2. Clone and extend.
0.
0, 8.

A[2] = 4. Case 3. Clone, extend and discard.
0.
0, 4.
0, 8. Discarded

A[3] = 12. Case 2. Clone and extend.
0.
0, 4.
0, 4, 12.

A[4] = 2. Case 3. Clone, extend and discard.
0.
0, 2.
0, 4. Discarded.
0, 4, 12.

A[5] = 10. Case 3. Clone, extend and discard.
0.
0, 2.
0, 2, 10.
0, 4, 12. Discarded.

A[6] = 6. Case 3. Clone, extend and discard.
0.
0, 2.
0, 2, 6.
0, 2, 10. Discarded.

A[7] = 14. Case 2. Clone and extend.
0.
0, 2.
0, 2, 6.
0, 2, 6, 14.

A[8] = 1. Case 3. Clone, extend and discard.
0.
0, 1.
0, 2. Discarded.
0, 2, 6.
0, 2, 6, 14.

A[9] = 9. Case 3. Clone, extend and discard.
0.
0, 1.
0, 2, 6.
0, 2, 6, 9.
0, 2, 6, 14. Discarded.

A[10] = 5. Case 3. Clone, extend and discard.
0.
0, 1.
0, 1, 5.
0, 2, 6. Discarded.
0, 2, 6, 9.

A[11] = 13. Case 2. Clone and extend.
0.
0, 1.
0, 1, 5.
0, 2, 6, 9.
0, 2, 6, 9, 13.

A[12] = 3. Case 3. Clone, extend and discard.
0.
0, 1.
0, 1, 3.
0, 1, 5. Discarded.
0, 2, 6, 9.
0, 2, 6, 9, 13.

A[13] = 11. Case 3. Clone, extend and discard.
0.
0, 1.
0, 1, 3.
0, 2, 6, 9.
0, 2, 6, 9, 11.
0, 2, 6, 9, 13. Discarded.

A[14] = 7. Case 3. Clone, extend and discard.
0.
0, 1.
0, 1, 3.
0, 1, 3, 7.
0, 2, 6, 9. Discarded.
0, 2, 6, 9, 11.

A[15] = 15. Case 2. Clone and extend.
0.
0, 1.
0, 1, 3.
0, 1, 3, 7.
0, 2, 6, 9, 11.
0, 2, 6, 9, 11, 15. <-- LIS List
```

设计算法需要了解以上策略。 另外，确保我们保持以下条件：**“较小列表的结束元素小于较大列表的结束元素”**。 在进一步阅读之前，请尝试其他一些示例。 重要的是要了解结束元素发生了什么。

## 算法实现

**算法**：

查询最长的长度相当容易。 请注意，我们仅处理末端元素。 我们不需要维护所有列表。 我们可以将结束元素存储在数组中。 丢弃操作可以通过替换进行模拟，并且扩展列表类似于向数组添加更多元素。

我们将使用辅助数组来保留结束元素。 该数组的最大长度是输入的长度。 在最坏的情况下，数组会分成`N`个大小为 1 的列表（**注意，这不会导致最坏情况下的复杂性**）。 要丢弃一个元素，我们将在辅助数组中跟踪`A[i]`的`ceil`值（再次观察您的粗略工作中的末端元素），并将`ceil`值替换为`A[i]`。 我们通过将元素添加到辅助数组来扩展列表。 我们还维护一个计数器来跟踪辅助数组的长度。

**Bonus:** You have learnt [Patience Sorting](http://en.wikipedia.org/wiki/Patience_sorting) technique partially 🙂

这是一个谚语，“**告诉我，我会忘记的。 给我看，我会记得。 让我参与进来，我会明白。**” 因此，从纸牌中选择一个牌组。 从经过打乱的牌组中找出卡片的最长的递增子序列。 您将永远不会忘记这种方法。 🙂

**更新 – 2016 年 7 月 17 日**：读者们的回响颇为深刻，很少有网站引用此帖子，感到很高兴，因为我为别人提供帮助而感到辛苦。 看来读者在发表评论之前没有做任何功课。 阅读本文后要求阅读一些示例，并请在纸上做您的工作（请勿使用编辑器/编译器）。 要求是帮助自己。 对“知道”的专业不同于真正的理解（不尊重）。 以下是我的个人经历。

**最初的内容准备工作大约花了我 6 个小时。 但是，这是一个很好的教训。 我在一个小时内完成了初始代码。 当我开始写内容向读者解释时，我意识到我不理解这些案例。 拿了我的笔记本（我习惯于装订绑定的笔记本以跟踪我的粗略工作），几个小时后，我填写了将近 15 页的粗略工作。 无论您在灰色示例中看到的内容是来自这些页面的。 我强烈建议您实践《Udi Manber 算法入门》一书中的注解触发解决方案的所有思考过程。**

我怀疑，许多读者可能无法理解`CeilIndex`（二分搜索）背后的逻辑。 我把它作为练习让读者理解它是如何工作的。 在纸上浏览几个示例。 我意识到我已经在[另一篇文章](https://www.geeksforgeeks.org/the-ubiquitous-binary-search-set-1/)中介绍了该算法。

**更新 – 2016 年 8 月 5 日**：

完成工作后，以下链接值得参考。 我通过最近创建的 **Disqus** 个人资料认识了该链接。 该链接具有 Wiki 中提到的方法的说明。

[http://stackoverflow.com/questions/2631726/how-to-determine-the-longest-increasing-subsequence-using-dynamic-programming](http://stackoverflow.com/questions/2631726/how-to-determine-the-longest-increasing-subsequence-using-dynamic-programming)

## 代码示例

下面给出的是查找 LIS 长度的代码（**更新为 C++ 11 代码，没有 C 样式的数组**），

### C++

```cpp
#include <iostream> 
#include <vector> 

// Binary search (note boundaries in the caller) 
int CeilIndex(std::vector<int>& v, int l, int r, int key) 
{ 
    while (r - l > 1) { 
        int m = l + (r - l) / 2; 
        if (v[m] >= key) 
            r = m; 
        else
            l = m; 
    } 

    return r; 
} 

int LongestIncreasingSubsequenceLength(std::vector<int>& v) 
{ 
    if (v.size() == 0) 
        return 0; 

    std::vector<int> tail(v.size(), 0); 
    int length = 1; // always points empty slot in tail 

    tail[0] = v[0]; 
    for (size_t i = 1; i < v.size(); i++) { 

        // new smallest value 
        if (v[i] < tail[0]) 
            tail[0] = v[i]; 

        // v[i] extends largest subsequence 
        else if (v[i] > tail[length - 1]) 
            tail[length++] = v[i]; 

        // v[i] will become end candidate of an existing 
        // subsequence or Throw away larger elements in all 
        // LIS, to make room for upcoming grater elements 
        // than v[i] (and also, v[i] would have already 
        // appeared in one of LIS, identify the location 
        // and replace it) 
        else
            tail[CeilIndex(tail, -1, length - 1, v[i])] = v[i]; 
    } 

    return length; 
} 

int main() 
{ 
    std::vector<int> v{ 2, 5, 3, 7, 11, 8, 10, 13, 6 }; 
    std::cout << "Length of Longest Increasing Subsequence is "
              << LongestIncreasingSubsequenceLength(v) << '\n'; 
    return 0; 
} 
```

## 参考资料

- [最长递增子序列 - 维基百科](http://en.wikipedia.org/wiki/Longest_increasing_subsequence)
- [耐心排序 - 维基百科](http://en.wikipedia.org/wiki/Patience_sorting)
- [二分查找的普遍性 - GeeksforGeeks](https://www.geeksforgeeks.org/the-ubiquitous-binary-search-set-1/)
- [Stack Overflow: 如何使用动态规划确定最长递增子序列](http://stackoverflow.com/questions/2631726/how-to-determine-the-longest-increasing-subsequence-using-dynamic-programming)

## Java

```java
// Java program to find length of longest increasing subsequence 
// in O(n Log n) time 
import java.io.*; 
import java.util.*; 
import java.lang.Math; 

class LIS { 
    // Binary search (note boundaries in the caller) 
    // `A[]` is `ceilIndex` in the caller 
    static int `CeilIndex`(`int A[]`, int l, int r, int key) 
    { 
        while (r - l > 1) { 
            int m = l + (r - l) / 2; 
            if (`A[m]` >= key) 
                r = m; 
            else
                l = m; 
        } 

        return r; 
    } 

    static int `LongestIncreasingSubsequenceLength`(`int A[]`, int size) 
    { 
        // Add boundary case, when array size is one 

        `int[] tailTable` = new int[size]; 
        int `len`; // always points empty slot 

        `tailTable[0]` = `A[0]`; 
        `len` = 1; 
        for (int i = 1; i < size; i++) { 
            if (`A[i]` < `tailTable[0]`) 
                // new smallest value 
                `tailTable[0]` = `A[i]`; 

            else if (`A[i]` > `tailTable[len - 1]`) 
                // `A[i]` wants to extend largest subsequence 
                `tailTable[len++]` = `A[i]`; 

            else
                // `A[i]` wants to be current end candidate of an existing 
                // subsequence. It will replace ceil value in `tailTable` 
                `tailTable[`CeilIndex(`tailTable`, -1, `len - 1`, `A[i]`)]` = `A[i]`; 
        } 

        return `len`; 
    } 

    // Driver program to test above function 
    public static void main(String[] args) 
    { 
        int A[] = { 2, 5, 3, 7, 11, 8, 10, 13, 6 }; 
        int n = A.length; 
        `System.out.println("Length of Longest Increasing Subsequence is " + LongestIncreasingSubsequenceLength(A, n))`; 
    } 
} 
/* This code is contributed by Devesh Agrawal*/
```

## Python3

```py
# Python program to find 
# length of longest 
# increasing subsequence 
# in O(n Log n) time 

# Binary search (note 
# boundaries in the caller) 
# `A[]` is `ceilIndex` 
# in the caller 
def `CeilIndex`(`A`, l, r, key): 

    while (r - l > 1): 

        m = l + (r - l)//2
        if (`A[m]` >= key): 
            r = m 
        else: 
            l = m 
    return r 

def `LongestIncreasingSubsequenceLength`(`A`, size): 

    # Add boundary case, 
    # when array size is one 

    `tailTable` = [0 for i in range(size + 1)] 
    `len` = 0 # always points empty slot 

    `tailTable[0]` = `A[0]` 
    `len` = 1
    for i in range(1, size): 

        if (`A[i]` < `tailTable[0]`): 

            # new smallest value 
            `tailTable[0]` = `A[i]` 

        elif (`A[i]` > `tailTable[len-1]`): 

            # `A[i]` wants to extend 
            # largest subsequence 
            `tailTable[len]` = `A[i]` 
            `len`+= 1

        else: 
            # `A[i]` wants to be current 
            # end candidate of an existing 
            # subsequence. It will replace 
            # ceil value in `tailTable` 
            `tailTable[`CeilIndex(`tailTable`, -1, `len-1`, `A[i]`)]` = `A[i]` 

    return `len`

# Driver program to 
# test above function 

A = [ 2, 5, 3, 7, 11, 8, 10, 13, 6 ] 
n = len(A) 

`print("Length of Longest Increasing Subsequence is ", LongestIncreasingSubsequenceLength(A, n))` 

# This code is contributed 
# by Anant Agarwal. 
```

## C#

```cs
// C# program to find length of longest 
// increasing subsequence in O(n Log n) 
// time 
using System; 

class GFG { 

    // Binary search (note boundaries 
    // in the caller) `A[]` is `ceilIndex` 
    // in the caller 
    static int `CeilIndex`(`int[] A`, int l, 
                         int r, int key) 
    { 
        while (r - l > 1) { 
            int m = l + (r - l) / 2; 

            if (`A[m]` >= key) 
                r = m; 
            else
                l = m; 
        } 

        return r; 
    } 

    static int `LongestIncreasingSubsequenceLength`(
        `int[] A`, int size) 
    { 

        // Add boundary case, when array size 
        // is one 

        `int[] tailTable` = new int[size]; 
        int `len`; // always points empty slot 

        `tailTable[0]` = `A[0]`; 
        `len` = 1; 
        for (int i = 1; i < size; i++) { 
            if (`A[i]` < `tailTable[0]`) 
                // new smallest value 
                `tailTable[0]` = `A[i]`; 

            else if (`A[i]` > `tailTable[len - 1]`) 

                // `A[i]` wants to extend largest 
                // subsequence 
                `tailTable[len++]` = `A[i]`; 

            else

                // `A[i]` wants to be current end 
                // candidate of an existing 
                // subsequence. It will replace 
                // ceil value in `tailTable` 
                `tailTable[`CeilIndex(`tailTable`, -1, 
                                    `len - 1`, `A[i]`)]` 
                    = `A[i]`; 
        } 

        return `len`; 
    } 

    // Driver program to test above function 
    public static void Main() 
    { 
        int[] A = { 2, 5, 3, 7, 11, 8, 10, 13, 6 }; 
        int n = A.Length; 
        `Console.Write("Length of Longest " + "Increasing Subsequence is " + LongestIncreasingSubsequenceLength(A, n))`; 
    } 
} 

// This code is contributed by nitin mittal. 
```

# PHP

```php
<?php 
// PHP program to find 
// length of longest 
// increasing subsequence 
// in O(n Log n) time 

// Binary search (note 
// boundaries in the caller) 
// A[] is ceilIndex 
// in the caller 
function CeilIndex($A, $l, $r, $key) 
{ 
    while ($r - $l > 1) 
    { 
        $m = (int)($l + ($r - $l)/2); 
        if ($A[$m] >= $key) 
            $r = $m; 
        else
            $l = $m; 
    } 
    return $r; 
} 

function LongestIncreasingSubsequenceLength($A, $size) 
{ 
    // Add boundary case, 
    // when array size is one 

    $tailTable = array_fill(0, ($size + 1), 0); 
    $len = 0; // always points empty slot 

    $tailTable[0] = $A[0]; 
    $len = 1; 
    for($i = 1; $i < $size; $i++) 
    { 

        if ($A[$i] < $tailTable[0]) 
            // new smallest value 
            $tailTable[0] = $A[$i]; 

        else if ($A[$i] > $tailTable[$len-1]) 
        { 
            // A[i] wants to extend 
            // largest subsequence 
            $tailTable[$len] = $A[$i]; 
            $len++; 
        } 
        else
            // A[i] wants to be current 
            // end candidate of an existing 
            // subsequence. It will replace 
            // ceil value in tailTable 
            $tailTable[CeilIndex($tailTable, -1, $len-1, $A[$i])] = $A[$i]; 

    } 
    return $len; 
} 

// Driver program to 
// test above function 
$A = array( 2, 5, 3, 7, 11, 8, 10, 13, 6 ); 
$n = count($A); 

print("Length of Longest Increasing Subsequence is ". 
        LongestIncreasingSubsequenceLength($A, $n)); 

// This code is contributed by chandan_jnu 
?>
```

### 输出

```
Length of Longest Increasing Subsequence is 6
```

### 复杂度

循环运行`N`个元素。 在最坏的情况下（什么是最坏情况的输入？），我们最终可能会使用二分搜索（`log i`）来查询许多`A[i]`的`ceil`值。

因此，`T(n) < O(log N!)= O(N log N)`。 分析以确保上限和下限也是`O(N log N)`。 复杂度为`THETA(N log N)`。

### 练习

1.  [设计一种算法，以构造最长的递增列表](https://www.geeksforgeeks.org/construction-of-longest-monotonically-increasing-subsequence-n-log-n/)。 另外，使用 DAG 对解决方案进行建模。

2.  设计一种算法，以构造**所有**的列表，这些列表具有相同的最长大小。

3.  上述算法是**在线**算法吗？

4.  设计一种算法来构造最长的**递减**列表。

[**在 C++ 中使用`lower_bound()`的替代实现**](https://www.geeksforgeeks.org/lower_bound-in-cpp/)

```cpp
#include<bits/stdc++.h> 
using namespace std; 

int LongestIncreasingSubsequenceLength(std::vector<int>& v) 
{ 
    if (v.size() == 0) 
        return 0; 

    std::vector<int> tail(v.size(), 0); 
    int length = 1; // always points empty slot in tail 

    tail[0] = v[0]; 

    for (int i = 1; i < v.size(); i++) { 

            // Do binary search for the element in 
            // the range from begin to begin + length 
        auto b = tail.begin(), e = tail.begin() + length; 
        auto it = lower_bound(b, e, v[i]); 

        // If not present change the tail element to v[i] 
        if (it == tail.begin() + length) 
        tail[length++] = v[i]; 
        else   
        *it = v[i]; 
    } 

    return length; 
} 

int main() 
{ 
    std::vector<int> v{ 2, 5, 3, 7, 11, 8, 10, 13, 6 }; 
    std::cout << "Length of Longest Increasing Subsequence is "
            << LongestIncreasingSubsequenceLength(v); 
    return 0; 
}
```

输出：

```
Length of Longest Increasing Subsequence is 6
```