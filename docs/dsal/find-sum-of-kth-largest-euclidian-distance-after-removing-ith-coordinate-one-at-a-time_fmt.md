# 一次去掉一个坐标后求第 k 个最大欧几里德距离的和

> 原文：[https://www.geeksforgeeks.org/find-sum-of-kth-largest-euclidian-distance-after-removing-ith-coordinate-one-at-a-time/](https://www.geeksforgeeks.org/find-sum-of-kth-largest-euclidian-distance-after-removing-ith-coordinate-one-at-a-time/)

给定 `N` 个整数坐标，其中 `X[i]` 表示 X 坐标，`Y[i]` 表示第 `i` 个坐标的 Y 坐标，任务是为 `i` 的所有可能值找到除第 `i` 个坐标之外的所有坐标对之间的第 `K` 个最大欧几里德距离之和。

**示例：**

> **输入：** `X[] = {0，0，1，1}`，`Y[] = {0，1，0，1}`，`K = 2`
> **输出：** 4
> **解释：**
> 1.  第一个坐标以外的坐标为 `{(0，1)，(1，0)，(1，1)}`。它们各自的欧几里得距离是 `{1.414，1，1}`。由于 `K = 2`，第二大欧几里德距离 = 1。
> 2.  第二个坐标以外的坐标为 `{(0，0)，(1，0)，(1，1)}`。它们各自的欧几里得距离是 `{1，1，1.414}`。第二大欧几里得距离 = 1。
> 3.  第三个坐标以外的坐标为 `{(0，1)，(0，0)，(1，1)}`。它们各自的欧几里得距离是 `{1，1.414，1}`。第二大欧几里得距离 = 1。
> 4.  除第四个坐标之外的坐标为 `{(0，1)，(1，0)，(0，0)}`。它们各自的欧几里得距离是 `{1.414，1，1}`。第二大欧几里得距离 = 1。
>
> 所有第二大欧几里得距离之和是 4。
>
> **输入：** `X[] = {0，1，1}`，`Y[] = {0，0，1}`，`K = 1`
> **输出：** 3.41421

## 方法

给定的问题可以通过以下步骤解决：
*   创建一个[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/) `distances[]`，该向量存储范围 `[1，N]` 内所有有效无序对 `(p，q)` 的索引 `p`、`q` 以及第 `p` 个和第 `q` 个坐标之间的欧几里德距离。
*   [按照距离递减的顺序对向量](https://www.geeksforgeeks.org/sorting-a-vector-in-c/) `distances` 进行排序。
*   对于范围 `[1，N]` 内的所有 `i` 值，执行以下操作：
    *   创建一个变量 `cnt`，它跟踪 `distances` 向量中第 `K` 个最大元素的索引。最初，`cnt = 0`。
    *   [使用变量 `j` 迭代向量](https://www.geeksforgeeks.org/iterators-c-stl/) `distances`，如果 `i != p` 和 `i != q`，其中 `(p，q)` 是存储在 `distances[j]` 中的坐标索引，则将 `cnt` 的值增加 `1`。
    *   如果 `cnt = K`，将 `distances` 向量中当前索引 `j` 处的距离添加到变量 `sum` 中。
    *   存储在 `sum` 中的值是必需的答案。

下面是上述方法的实现：

### C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the sum of the Kth
// maximum distance after excluding the
// ith coordinate for all i over the
// range [1, N]
double sumMaxDistances(int X[], int Y[],
                       int N, int K)
{
    // Stores (p, q) and the square of
    // distance between pth and qth
    // coordinate
    vector<pair<int, pair<int, int> > > distances;

    // Find the euclidian distances
    // between all pairs of coordinates
    for (int i = 0; i < N; i++) {
        for (int j = i + 1; j < N; j++) {

            // Stores the square of euclidian
            // distance between the ith and
            // the jth coordinate
            int d = (X[i] - X[j]) * (X[i] - X[j])
                    + (Y[i] - Y[j]) * (Y[i] - Y[j]);

            // Insert into distances
            distances.push_back({ d, { i, j } });
        }
    }

    // Stores the final answer
    double ans = 0;

    // Sort the distances vector in the
    // decreasing order of distance
    sort(distances.begin(), distances.end(),
         greater<pair<int, pair<int, int> > >());

    // Iterate over all i in range [1, N]
    for (int i = 0; i < N; i++) {

        // Stores the square of Kth maximum
        // distance
        int mx = -1;

        // Stores the index of Kth maximum
        // distance
        int cnt = 0;

        // Loop to iterate over distances
        for (int j = 0; j < distances.size(); j++) {

            // Check if any of (p, q) in
            // distances[j] is equal to i
            if (distances[j].second.first != i
                && distances[j].second.second != i) {
                cnt++;
            }

            // If the current index is the
            // Kth largest distance
            if (cnt == K) {
                mx = distances[j].first;
                break;
            }
        }

        // If Kth largest distance exists
        // then add it into ans
        if (mx != -1) {

            // Add square root of mx as mx
            // stores the square of distance
            ans += sqrt(mx);
        }
    }

    // Return the result
    return ans;
}

// Driver Code
int main()
{
    int X[] = { 0, 1, 1 };
    int Y[] = { 0, 0, 1 };
    int K = 1;
    int N = sizeof(X) / sizeof(X[0]);

    cout << sumMaxDistances(X, Y, N, K);

    return 0;
}
```

### Java

```java
// Java code for the above approach
import java.io.*;
import java.util.*;
import java.util.Collections;

// User defined Pair class
class Pair {
    int first;
    int second;

    // Constructor
    public Pair(int first, int second)
    {
        this.first = first;
        this.second = second;
    }
}

// User defined Pair with one element int and other as a
// pair
class Pair_next {
    int first;
    Pair second;

    // constructor
    public Pair_next(int first, Pair second)
    {
        this.first = first;
        this.second = second;
    }
}

// class to sort the elements in
// decreasing order of first element
class cmp implements Comparator<Pair_next> {

    public int compare(Pair_next p1, Pair_next p2)
    {
        return p2.first - p1.first;
    }
}

public class GFG {

    // Function to find the sum of the Kth
    // maximum distance after excluding the
    // ith coordinate for all i over the
    // range [1, N]
    static double sumMaxDistances(int X[], int Y[], int N,
                                  int K)
    {

        // Stores (p, q) and the square of
        // distance between pth and qth
        // coordinate
        Vector<Pair_next> distances
            = new Vector<Pair_next>();

        // Find the euclidian distances
        // between all pairs of coordinates
        for (int i = 0; i < N; i++) {
            for (int j = i + 1; j < N; j++) {

                // Stores the square of euclidian
                // distance between the ith and
                // the jth coordinate
                int d = (X[i] - X[j]) * (X[i] - X[j])
                    + (Y[i] - Y[j]) * (Y[i] - Y[j]);

                // Insert into distances
                Pair temp_pair = new Pair(i, j);
                Pair_next temp
                    = new Pair_next(d, temp_pair);

                distances.add(temp);
            }
        }

        // Stores the final answer
        double ans = 0;

        // Sort the distances vector in the
        // decreasing order of distance
        Collections.sort(distances, new cmp());

        // Iterate over all i in range [1, N]
        for (int i = 0; i < N; i++) {

            // Stores the square of Kth maximum
            // distance
            int mx = -1;

            // Stores the index of Kth maximum
            // distance
            int cnt = 0;

            // Loop to iterate over distances
            for (int j = 0; j < distances.size(); j++) {

                // Check if any of (p, q) in
                // distances[j] is equal to i
                if (distances.get(j).second.first != i
                    && distances.get(j).second.second
                        != i) {
                    cnt++;
                }

                // If the current index is the
                // Kth largest distance
                if (cnt == K) {
                    mx = distances.get(j).first;
                    break;
                }
            }

            // If Kth largest distance exists
            // then add it into ans
            if (mx != -1) {

                // Add square root of mx as mx
                // stores the square of distance
                ans += Math.sqrt(mx);
            }
        }

        // Return the result
        return ans;
    }

    // Driver Code
    public static void main(String[] args)
    {
        int X[] = { 0, 1, 1 };
        int Y[] = { 0, 0, 1 };
        int K = 1;
        int N = X.length;

        System.out.println(sumMaxDistances(X, Y, N, K));
    }
}

// This code is contributed by rj13to.
```

### Python 3

```python
# Python 3 program for the above approach
from math import sqrt

# Function to find the sum of the Kth
# maximum distance after excluding the
# ith coordinate for all i over the
# range [1, N]
def sumMaxDistances(X, Y, N, K):

    # Stores (p, q) and the square of
    # distance between pth and qth
    # coordinate
    distances = []

    # Find the euclidian distances
    # between all pairs of coordinates
    for i in range(N):
        for j in range(i + 1, N, 1):

            # Stores the square of euclidian
            # distance between the ith and
            # the jth coordinate
            d = int(X[i] - X[j]) * int(X[i] - X[j]) + int(Y[i] - Y[j]) * int(Y[i] - Y[j])

            # Insert into distances
            distances.append([d,[i, j]])

    # Stores the final answer
    ans = 0

    # Sort the distances vector in the
    # decreasing order of distance
    distances.sort(reverse = True)

    # Iterate over all i in range [1, N]
    for i in range(N):

        # Stores the square of Kth maximum
        # distance
        mx = -1

        # Stores the index of Kth maximum
        # distance
        cnt = 0
```

## Driver Code

```python
# Loop to iterate over distances
for j in range(0, len(distances), 1):
    # Check if any of (p, q) in distances[j] is equal to i
    if (distances[j][1][0] != i and distances[j][1][0] != i):
        cnt += 1

    # If the current index is the Kth largest distance
    if (cnt == K):
        mx = distances[j][0]
        break

# If Kth largest distance exists then add it into ans
if (mx != -1):
    # Add square root of mx as mx stores the square of distance
    ans += (sqrt(mx))

# Return the result
return ans

if __name__ == '__main__':
    X = [0, 1, 1]
    Y = [0, 0, 1]
    K = 1
    N = len(X)
    print(sumMaxDistances(X, Y, N, K))
```

### Output

```
3.41421
```

**时间复杂度:** `O(N^2 * log N + K * N^2)`
**辅助空间:** `O(N^2)`