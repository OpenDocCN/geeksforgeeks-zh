# 高速公路广告牌问题

> 原文: [https://www.geeksforgeeks.org/highway-billboard-problem/](https://www.geeksforgeeks.org/highway-billboard-problem/)

考虑一条 `M` 英里的高速公路。任务是在高速公路上放置广告牌，以使收入最大化。广告牌的可能位置由编号 `x1, x2, ..., xn-1, xn` 给出，指定从道路一端开始测量的以英里为单位的位置。如果我们在 `xi` 位置放置广告牌，我们将获得 `ri > 0` 的收入。有一个限制，在 `t` 英里以内不能放置两块广告牌。
注意: 从 `x1` 到 `xn` 的所有可能地点都在 0 到 `M` 的范围内，因为需要在 `M` 英里的高速公路上放置广告牌。

**举例:**

```
Input : M = 20
        x[]       = {6, 7, 12, 13, 14}
        revenue[] = {5, 6, 5,  3,  1}
        t = 5
Output: 10
By placing two billboards at 6 miles and 12
miles will produce the maximum revenue of 10.

Input : M = 15
        x[] = {6, 9, 12, 14}
        revenue[] = {5, 6, 3, 7}
        t = 2
Output : 18
```

让 `maxRev[i]`，`1 <= i <= M`，表示从高速公路起点到 `i` 英里处产生的最大收入。现在对于高速公路上的每一英里，我们需要检查这一英里是否有任何广告牌的选项，如果没有，那么到这一英里的最大收入将与到前一英里的最大收入相同。但如果那一英里有广告牌选项，那么我们有两个选择：
1. 要么我们放置广告牌，忽略之前 `t` 英里内的广告牌，加上放置广告牌的收益。
2. 忽略这个广告牌。
所以 `maxRev[i] = max(maxRev[i-t-1] + revenue[i]， maxRev[i-1])`

下面是这个方法的实现:

## C++

```cpp
// C++ program to find maximum revenue by placing
// billboard on the highway with given constraints.
#include<bits/stdc++.h>
using namespace std;

int maxRevenue(int m, int x[], int revenue[], int n, int t)
{
    // Array to store maximum revenue at each miles.
    int maxRev[m+1];
    memset(maxRev, 0, sizeof(maxRev));

    // actual minimum distance between 2 billboards.
    int nxtbb = 0;
    for (int i = 1; i <= m; i++)
    {
        // check if all billboards are already placed.
        if (nxtbb < n)
        {
            // check if we have billboard for that particular
            // mile. If not, copy the previous maximum revenue.
            if (x[nxtbb] != i)
                maxRev[i] = maxRev[i-1];

            // we do have billboard for this mile.
            else
            {
                // We have 2 options, we either take current
                // or we ignore current billboard.

                // If current position is less than or equal to
                // t, then we can have only one billboard.
                if (i <= t)
                    maxRev[i] = max(maxRev[i-1], revenue[nxtbb]);

                // Else we may have to remove previously placed
                // billboard
                else
                    maxRev[i] = max(maxRev[i-t-1]+revenue[nxtbb],
                                    maxRev[i-1]);

                nxtbb++;
            }
        }
        else
            maxRev[i] = maxRev[i - 1];
    }

    return maxRev[m];
}

// Driven Program
int main()
{
    int m = 20;
    int x[] = {6, 7, 12, 13, 14};
    int revenue[] = {5, 6, 5, 3, 1};
    int n = sizeof(x)/sizeof(x[0]);
    int t = 5;
    cout << maxRevenue(m, x, revenue, n, t) << endl;
    return 0;
}
```

## Java

```java
// Java program to find maximum revenue
// by placing billboard on the highway
// with given constraints.

class GFG
{

static int maxRevenue(int m, int[] x,
                    int[] revenue,
                    int n, int t)
{

    // Array to store maximum revenue
    // at each miles.
    int[] maxRev = new int[m + 1];
    for(int i = 0; i < m + 1; i++)
        maxRev[i] = 0;

    // actual minimum distance between
    // 2 billboards.
    int nxtbb = 0;
    for (int i = 1; i <= m; i++)
    {
        // check if all billboards are
        // already placed.
        if (nxtbb < n)
        {
            // check if we have billboard for
            // that particular mile. If not,
            // copy the previous maximum revenue.
            if (x[nxtbb] != i)
                maxRev[i] = maxRev[i - 1];

            // we do have billboard for this mile.
            else
            {
                // We have 2 options, we either take
                // current or we ignore current billboard.

                // If current position is less than or
                // equal to t, then we can have only
                // one billboard.
                if (i <= t)
                    maxRev[i] = Math.max(maxRev[i - 1],
                                        revenue[nxtbb]);

                // Else we may have to remove
                // previously placed billboard
                else
                    maxRev[i] = Math.max(maxRev[i - t - 1] +
                                        revenue[nxtbb],
                                        maxRev[i - 1]);

                nxtbb++;
            }
        }
        else
            maxRev[i] = maxRev[i - 1];
    }

    return maxRev[m];
}

// Driver Code
public static void main(String []args)
{
    int m = 20;
    int[] x = new int[]{6, 7, 12, 13, 14};
    int[] revenue = new int[]{5, 6, 5, 3, 1};
    int n = x.length;
    int t = 5;
    System.out.println(maxRevenue(m, x, revenue, n, t));
}
}

// This code is contributed by Ita_c.
```

## Python 3

```python
# Python3 program to find maximum revenue
# by placing billboard on the highway with
# given constraints.

def maxRevenue(m, x, revenue, n, t) :

    # Array to store maximum revenue
    # at each miles.
    maxRev = [0] * (m + 1)

    # actual minimum distance between
    # 2 billboards.
    nxtbb = 0;
    for i in range(1, m + 1) :

        # check if all billboards are
        # already placed.
        if (nxtbb < n) :

            # check if we have billboard for
            # that particular mile. If not,
            # copy the previous maximum revenue.
            if (x[nxtbb] != i) :
                maxRev[i] = maxRev[i - 1]

            # we do have billboard for this mile.
            else :

                # We have 2 options, we either take
                # current or we ignore current billboard.

                # If current position is less than or
                # equal to t, then we can have only
                # one billboard.
                if (i <= t) :
                    maxRev[i] = max(maxRev[i - 1],
                                    revenue[nxtbb])

                # Else we may have to remove
                # previously placed billboard
                else :
                    maxRev[i] = max(maxRev[i - t - 1] +
                                    revenue[nxtbb],
                                    maxRev[i - 1]);

                nxtbb += 1

        else :

            maxRev[i] = maxRev[i - 1]

    return maxRev[m]

# Driver Code
if __name__ == "__main__" :

    m = 20
    x = [6, 7, 12, 13, 14]
    revenue = [5, 6, 5, 3, 1]
    n = len(x)
    t = 5
    print(maxRevenue(m, x, revenue, n, t))

# This code is contributed by Ryuga
```

## C#

```csharp
// C# program to find maximum revenue
// by placing billboard on the highway
// with given constraints.
using System;

class GFG
{
    static int maxRevenue(int m, int[] x,
                          int[] revenue,
                          int n, int t)
    {
        // Array to store maximum revenue
        // at each miles.
        int[] maxRev = new int[m + 1];
        for(int i = 0; i < m + 1; i++)
            maxRev[i] = 0;

        // actual minimum distance between
        // 2 billboards.
        int nxtbb = 0;
        for (int i = 1; i <= m; i++)
        {
            // check if all billboards are
            // already placed.
            if (nxtbb < n)
            {
                // check if we have billboard for
                // that particular mile. If not,
                // copy the previous maximum revenue.
                if (x[nxtbb] != i)
                    maxRev[i] = maxRev[i - 1];

                // we do have billboard for this mile.
                else
                {
                    // We have 2 options, we either take
                    // current or we ignore current billboard.

                    // If current position is less than or
                    // equal to t, then we can have only
                    // one billboard.
                    if (i <= t)
                        maxRev[i] = Math.Max(maxRev[i - 1],
                                             revenue[nxtbb]);

                    // Else we may have to remove
                    // previously placed billboard
                    else
                        maxRev[i] = Math.Max(maxRev[i - t - 1] +
                                             revenue[nxtbb],
                                             maxRev[i - 1]);

                    nxtbb++;
                }
            }
            else
                maxRev[i] = maxRev[i - 1];
        }

        return maxRev[m];
    }

    // Driver Code
    static void Main()
    {
        int m = 20;
        int[] x = new int[]{6, 7, 12, 13, 14};
        int[] revenue = new int[]{5, 6, 5, 3, 1};
        int n = x.Length;
        int t = 5;
        Console.Write(maxRevenue(m, x, revenue, n, t));
    }
}

// This code is contributed by DrRoot_
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```php
<?php
// PHP program to find
// maximum revenue by
// placing billboard on
// the highway with given
// constraints.

function maxRevenue($m, $x,
                    $revenue,
                    $n, $t)

{
    // Array to store maximum
    // revenue at each miles.
    $maxRev = array_fill(0, $m + 1,
                            false);

    // actual minimum distance
    // between 2 billboards.
    $nxtbb = 0;
    for ($i = 1; $i <= $m; $i++)
    {
        // check if all billboards
        // are already placed.
        if ($nxtbb < $n)
        {
            // check if we have billboard
            // for that particular
            // mile. If not, copy the
            // previous maximum revenue.
            if ($x[$nxtbb] != $i)
                $maxRev[$i] = $maxRev[$i - 1];

            // we do have billboard
            // for this mile.
            else
            {
                // We have 2 options,
                // we either take
                // current or we ignore
                // current billboard.

                // If current position is
                // less than or equal to
                // t, then we can have only
                // one billboard.
                if ($i <= $t)
                    $maxRev[$i] = max($maxRev[$i - 1],
                                      $revenue[$nxtbb]);

                // Else we may have to
                // remove previously
                // placed billboard
                else
                    $maxRev[$i] = max($maxRev[$i - $t - 1] +
                                      $revenue[$nxtbb],
                                      $maxRev[$i - 1]);
                $nxtbb++;
            }
        }
        else
            $maxRev[$i] = $maxRev[$i - 1];
    }

    return $maxRev[$m];
}

// Driver Code
$m = 20;
$x = array(6, 7, 12, 13, 14);
$revenue = array(5, 6, 5, 3, 1);
$n = sizeof($x);
$t = 5;
echo maxRevenue($m, $x,
                $revenue, $n, $t);

// This code is contributed by ajit
?>
```

## java 描述语言

```javascript
<script>

// Javascript program to find maximum revenue
// by placing billboard on the highway
// with given constraints.

    function maxRevenue(m,x,revenue,n,t)
    {
    // Array to store maximum revenue
    // at each miles.
    let maxRev = new Array(m + 1);
    for(let i = 0; i < m + 1; i++)
        maxRev[i] = 0;

    // actual minimum distance between
    // 2 billboards.
    let nxtbb = 0;
    for (let i = 1; i <= m; i++)
    {
        // check if all billboards are
        // already placed.
        if (nxtbb < n)
        {
            // check if we have billboard for
            // that particular mile. If not,
            // copy the previous maximum revenue.
            if (x[nxtbb] != i)
                maxRev[i] = maxRev[i - 1];

            // we do have billboard for this mile.
            else
            {
                // We have 2 options, we either take
                // current or we ignore current billboard.

                // If current position is less than or
                // equal to t, then we can have only
                // one billboard.
                if (i <= t)
                    maxRev[i] = Math.max(maxRev[i - 1],
                                        revenue[nxtbb]);

                // Else we may have to remove
                // previously placed billboard
                else
                    maxRev[i] = Math.max(maxRev[i - t - 1] +
                                        revenue[nxtbb],
                                        maxRev[i - 1]);

                nxtbb++;
            }
        }
        else
            maxRev[i] = maxRev[i - 1];
    }

    return maxRev[m];
    }

    // Driver Code
    let  m = 20;
    let x=[6, 7, 12, 13, 14];
    let revenue=[5, 6, 5, 3, 1];
    let n = x.length;
    let t = 5;
    document.write(maxRevenue(m, x, revenue, n, t));

    // This code is contributed by rag2127

</script>
```

**输出:**

**时间复杂度:** `O(M)`，其中 `M` 为总公路的距离。
**辅助空间:** `O(M)`。
**来源:**
[https://courses.cs.washington.edu/courses/cse421/06au/slides/Lecture18/Lecture18.pdf](https://courses.cs.washington.edu/courses/cse421/06au/slides/Lecture18/Lecture18.pdf)
本文由 `Anuj Chauhan` 供稿。如果你喜欢 `GeeksforGeeks` 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 `review-team@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。