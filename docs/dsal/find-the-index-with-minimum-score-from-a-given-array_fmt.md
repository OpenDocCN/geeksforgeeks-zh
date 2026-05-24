# 从给定数组中找到得分最小的索引

> 原文：[https://www.geeksforgeeks.org/find-the-index-with-minimum-score-from-a-given-array/](https://www.geeksforgeeks.org/find-the-index-with-minimum-score-from-a-given-array/)

给定一个大小为 `N`（`1 ≤ N ≤ 10^5`）的[数组](https://www.geeksforgeeks.org/array-data-structure/) `A[]`，由正整数组成，其中范围 `[0, N–1]` 内的索引 `i` 的得分定义为：

> `score[i] = A[i] * ((i + A[i] < N) ? score(i + A[i]) : 1)`

任务是找到得分最低的索引。

**示例：**

> **输入：** `A[] = {1, 2, 3, 4, 5}`
> **输出：** `2`
> **说明：**
> - `score[4] = 5 * 1 = 5`
> - `score[3] = 4 * 1 = 4`
> - `score[2] = 3 * 1 = 3`（*最小值*）
> - `score[1] = 2 * score[3] = 2 * 4 = 8`
> - `score[0] = 1 * score[1] = 1 * 8 = 8`

> **输入：** `A[] = {9, 8, 1, 2, 3, 6}`
> **输出：** `4`

**方法：** 按照以下步骤解决问题：

1.  [反向遍历数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/)，即从 `i = N–1` 迭代到 `0`。
2.  对于每一个 `i`，检查 `(A[i] + i)` 是否小于 `N`。
3.  将索引 `i` 的 `score[i]` 更新为 `score[i] = A[i] * ((i + A[i] < N) ? score(i + A[i]) : 1)`。
4.  打印最低分数的索引。

**以下是上述方法的实现：**

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the index with minimum score
void Min_Score_Index(int N, vector<int> A){
    // Stores the score of current index
    vector<int> Score(N, 0);

    // Traverse the array in reverse
    for (int i = N - 1; i >= 0; i--){
        if (A[i] + i < N)
            Score[i] = A[i] * Score[A[i] + i];
        else
            Score[i] = A[i];
    }

    // Update minimum score
    int min_value = INT_MAX;
    for(int i : Score) min_value = min(i, min_value);

    // Print the index with minimum score
    int ind = 0;
    for(int i = 0; i < N; i++){
        if(Score[i] == min_value) ind = i;
    }
    cout << (ind);
}

// Driver Code
int main(){
    int N = 5;
    vector<int> A = {1, 2, 3, 4, 5};
    Min_Score_Index(N, A);
}
```

## Java

```java
// Java program for the above approach
import java.util.*;

class GFG {
    // Function to find the index with minimum score
    static void Min_Score_Index(int N, int[] A) {
        // Stores the score of current index
        int[] Score = new int[N];

        // Traverse the array in reverse
        for (int i = N - 1; i >= 0; i--) {
            if (A[i] + i < N)
                Score[i] = A[i] * Score[A[i] + i];
            else
                Score[i] = A[i];
        }

        // Update minimum score
        int min_value = Integer.MAX_VALUE;
        for (int i : Score) min_value = Math.min(i, min_value);

        // Print the index with minimum score
        int ind = 0;
        for (int i = 0; i < N; i++) {
            if (Score[i] == min_value)
                ind = i;
        }
        System.out.print(ind);
    }

    // Driver Code
    public static void main(String[] args) {
        int N = 5;
        int[] A = {1, 2, 3, 4, 5};
        Min_Score_Index(N, A);
    }
}
// This code is contributed by 29AjayKumar
```

## Python 3

```python
# Python3 program for the above approach

# Function to find the index with minimum score
def Min_Score_Index(N, A):
    # Stores the score of current index
    Score = [0] * N

    # Traverse the array in reverse
    for i in range(N - 1, -1, -1):
        if A[i] + i < N:
            Score[i] = A[i] * Score[A[i] + i]
        else:
            Score[i] = A[i]

    # Update minimum score
    min_value = min(Score)

    # Print the index with minimum score
    ind = Score.index(min_value)
    print(ind)

# Driver Code
if __name__ == "__main__":
    N = 5
    A = [1, 2, 3, 4, 5]
    Min_Score_Index(N, A)
# This code is contributed by mohit kumar 29
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG {
    // Function to find the index with minimum score
    static void Min_Score_Index(int N, int[] A) {
        // Stores the score of current index
        int[] Score = new int[N];

        // Traverse the array in reverse
        for (int i = N - 1; i >= 0; i--) {
            if (A[i] + i < N)
                Score[i] = A[i] * Score[A[i] + i];
            else
                Score[i] = A[i];
        }

        // Update minimum score
        int min_value = Int32.MaxValue;
        foreach (int i in Score) {
            min_value = Math.Min(i, min_value);
        }

        // Print the index with minimum score
        int ind = 0;
        for (int i = 0; i < N; i++) {
            if (Score[i] == min_value)
                ind = i;
        }
        Console.WriteLine(ind);
    }

    // Driver Code
    public static void Main() {
        int N = 5;
        int[] A = { 1, 2, 3, 4, 5 };
        Min_Score_Index(N, A);
    }
}
// This code is contributed by chitranayal
```

## JavaScript

```javascript
<script>
// JavaScript program for the above approach

// Function to find the index with minimum score
function Min_Score_Index(N, A) {
    // Stores the score of current index
    var Score = Array(N).fill(0);

    // Traverse the array in reverse
    for (var i = N - 1; i >= 0; i--) {
        if (A[i] + i < N)
            Score[i] = A[i] * Score[A[i] + i];
        else
            Score[i] = A[i];
    }

    // Update minimum score
    var min_value = 1000000000;
    Score.forEach(i => {
        min_value = Math.min(i, min_value);
    });

    // Print the index with minimum score
    var ind = 0;
    for (var i = 0; i < N; i++) {
        if (Score[i] == min_value) ind = i;
    }
    document.write(ind);
}

// Driver Code
var N = 5;
var A = [1, 2, 3, 4, 5];
Min_Score_Index(N, A);
</script>
```

**输出：**

```
2
```

**时间复杂度：** `O(N)`
**辅助空间：** `O(N)`