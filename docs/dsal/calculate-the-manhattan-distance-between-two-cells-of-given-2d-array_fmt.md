# 计算给定 2D 阵列的两个单元之间的曼哈顿距离

> 原文: [https://www.geeksforgeeks.org/calculate-the-manhattan-distance-between-two-cells-of-given-2d-array/](https://www.geeksforgeeks.org/calculate-the-manhattan-distance-between-two-cells-of-given-2d-array/)

给定一个大小为 `M` * `N` 的 [2D 阵列](https://www.geeksforgeeks.org/multidimensional-arrays-in-java/)和形式为 `(X₁, Y₁)` 和 `(X₂, Y₂)` 的两个点，其中 `X₁` 和 `X₂` 代表行，`Y₁` 和 `Y₂` 代表列，任务是计算[给定点之间的曼哈顿距离](https://en.wikipedia.org/wiki/Taxicab_geometry)。

## 示例

> **输入:** `M = 5`，`N = 5`，`X₁ = 1`，`Y₁ = 2`，`X₂ = 3`，`Y₂ = 3`
> **输出:** `3`
> **说明:** 根据定义，曼哈顿距离等于坐标绝对差之和。
>
> **输入:** `M = 5`，`N = 5`，`X₁ = 4`，`Y₁ = 2`，`X₂ = 4`，`Y₂ = 2`
> **输出:** `0`

## 方法

该方法基于数学观察。两点之间的**曼哈顿距离**是坐标绝对差的总和。

> **曼哈顿距离** = `|X₁ – X₂| + |Y₁ – Y₂|`

下面是上述方法的实现。

## C++

```cpp
// C++ code to implement above approach
#include <bits/stdc++.h>
using namespace std;

// Code to calculate Manhattan distance
int manhattanDist(int M, int N, int X1, int Y1, int X2, int Y2)
{
    int dist = abs(X2 - X1) + abs(Y2 - Y1);
    return dist;
}

// Driver code
int main()
{
    // Define size of 2-D array
    int M = 5, N = 5;

    // First point
    int X1 = 1, Y1 = 2;

    // Second point
    int X2 = 3, Y2 = 3;

    cout << manhattanDist(M, N, X1, Y1, X2, Y2);
    return 0;
}
```

**输出**

```
3
```

**时间复杂度:** `O(1)`
**辅助空间:** `O(1)`