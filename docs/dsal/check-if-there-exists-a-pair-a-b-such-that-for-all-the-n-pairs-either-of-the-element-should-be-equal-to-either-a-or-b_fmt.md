# 检查是否存在一对(a，b)，使得对于所有的 N 对，任一元素应等于 a 或 b

> 原文: [https://www.geeksforgeeks.org/check-if-there-exists-a-pair-a-b-such-that-for-all-the-n-pairs-either-of-the-element-should-be-equal-to-either-a-or-b/](https://www.geeksforgeeks.org/check-if-there-exists-a-pair-a-b-such-that-for-all-the-n-pairs-either-of-the-element-should-be-equal-to-either-a-or-b/)

给定不同整数对的数组 `arr[]` 和 `N` 对，任务是检查是否存在任何对 `(X, Y)`，使得数组的每一对与对 `(X, Y)` 至少有一个公共元素。

**示例:**

> **输入:** `arr[] = {{1, 2}, {2, 3}, {3, 4}, {4, 5}}`
> **输出:** 是
> **说明:**
> 满足条件的一对是(2，4)。
>
> **输入:** `arr[] = {{1, 2}, {2, 3}, {3, 4}, {4, 5}, {5, 6}}`
> **输出:** 无
> **说明:**
> 无配对满足条件。

**方法:** 给定的问题可以基于以下观察来解决:

> 1.  It can be observed that if there is a pair of `(x, y)`, then either `arr[0].first` will be equal to `x` or `y` or `arr[0].second` will be equal to `x` or `y`.
> 2.  Because each pair has different elements, if an element appears `x` times in `x` pairs, then it must exist in all pairs.
> 3.  Therefore, if `(p, q)` is the required pair, and `f` is the count of the pair without elements in common with `p`, then `q` will be equal to appearing in the pair without elements in common with `p`.

按照以下步骤解决问题:

*   初始化一个整数变量，比如说 `counter`，来计算配对的数量，其中配对的两个元素都不等于 `X`。
*   另外，初始化一个向量表示 `frequency` 来存储元素的频率。
*   首先将变量 `X` 初始化为 `arr[0].first`。
*   现在使用变量 `i` 遍历数组 `arr[]`，并执行以下步骤:
    *   如果 `arr[i].first` 和 `arr[i].second` 两者不等于 `X`，则 `frequency` 的增量为 `arr[i].first` 和 `arr[i].second`，然后将 `counter` 增加 `1`。
*   如果阵频的最大频率等于 `counter`，则打印“是”返回。
*   否则，分配 `arr[0].second` 到 `X`，然后再次执行上述步骤。
*   最后，完成以上步骤后，如果以上情况都不满足，则打印“否”。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to check whether there exists
// a pair with given condition
string CommonPairs(int N, vector<pair<int, int> > arr)
{
    vector<int> V = { arr[0].first, arr[0].second };

    for (int x : V) {

        // Stores the frequency of elements
        vector<int> frequency(N + 1, 0);

        // Stores the count of the number
        // of pairs with no element equal
        // to x
        int counter = 0;

        // Traverse the array arr[]
        for (auto c : arr) {
            // If both the elements are not
            // equal to x
            if (c.first != x && c.second != x) {

                // Increment count of c.first
                // c.second by 1
                frequency[c.first]++;
                frequency[c.second]++;

                // Increment count by 1
                counter++;
            }
        }

        int M = *max_element(frequency.begin(),
                             frequency.end());

        // If maximum frequency is equal to counter
        if (M == counter) {
            return "Yes";
        }
    }

    // Return No
    return "No";
}

// Driver Code
int main()
{
    // Given Input
    vector<pair<int, int> > arr
        = { { 1, 2 }, { 2, 3 }, { 3, 4 }, { 4, 5 } };
    int N = arr.size();

    // Function Call
    cout << CommonPairs(N, arr);
}
```

## Python 3

```python
# python 3 program for the above approach

# Function to check whether there exists
# a pair with given condition
def CommonPairs(N, arr):

    V = (arr[0][0], arr[0][1])

    for x in V:

        # Stores the frequency of elements
        frequency = [0] * (N + 2)

        # Stores the count of the number
        # of pairs with no element equal
        # to x
        counter = 0

        # Traverse the array arr[]
        for c in arr:

            # If both the elements are not
            # equal to x
            if (c[0] != x and c[1] != x):

                # Increment count of c.first
                # c.second by 1
                frequency[c[0]] += 1
                frequency[c[1]] += 1

                # Increment count by 1
                counter += 1

        M = max(frequency)

        # If maximum frequency is equal to counter
        if (M == counter):
            return "Yes"

    # Return No
    return "No"

# Driver Code
if __name__ == "__main__":

    # Given Input
    arr = [[1, 2], [2, 3], [3, 4], [4, 5]]
    N = len(arr)

    # Function Call
    print(CommonPairs(N, arr))

# This code is contributed by ukasp.
```

## JavaScript

```javascript
<script>
// Javascript program for the above approach

// Function to check whether there exists
// a pair with given condition
function CommonPairs(N, arr) {

    let V = [arr[0][0], arr[0][1]];

    for (let x of V) {

        // Stores the frequency of elements
        let frequency = new Array(N + 1).fill(0);

        // Stores the count of the number
        // of pairs with no element equal
        // to x
        let counter = 0;

        // Traverse the array arr[]
        for (let c of arr) {
            // If both the elements are not
            // equal to x
            if (c[0] != x && c[1] != x) {

                // Increment count of c[0]
                // c[1] by 1
                frequency[c[0]]++;
                frequency[c[1]]++;

                // Increment count by 1
                counter++;
            }
        }

        let M = [...frequency].sort((a, b) => b - a)[0];

        // If maximum frequency is equal to counter
        if (M == counter) {
            return "Yes";
        }
    }

    // Return No
    return "No";
}

// Driver Code

// Given Input
let arr = [[1, 2], [2, 3], [3, 4], [4, 5]];
let N = arr.length;

// Function Call
document.write(CommonPairs(N, arr));

// This code is contributed by gfgking.
</script>
```

**输出**

```
Yes
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`