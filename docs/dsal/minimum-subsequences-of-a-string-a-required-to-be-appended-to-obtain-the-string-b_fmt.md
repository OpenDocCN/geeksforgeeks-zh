# 为获得字符串 B 需要追加的字符串 A 的最小子序列

> 原文：[https://www.geeksforgeeks.org/minimum-subsequences-of-a-string-a-required-to-be-appended-to-obtain-the-string-b/](https://www.geeksforgeeks.org/minimum-subsequences-of-a-string-a-required-to-be-appended-to-obtain-the-string-b/)

给定两个字符串 `A` 和 `B`，任务是通过以下操作计算构造字符串 `B` 所需的最小操作次数：

*   选择字符串 `A` 的一个子序列。
*   在新形成的字符串中添加该子序列（最初为空）。

打印所需的最小操作数。如果应用给定的操作无法使新字符串等于 `B`，则打印 `-1`。

## 示例

> **输入：** `A = "ABC"`，`B = "ABAC"`
> **输出：** `2`
> **说明：**
> 最初，`C = ""`。
> **第一步：** 从字符串 `A` 中选择子序列 `"AB"`，并将其追加到空字符串 `C` 中，即 `C = "AB"`。
> **第二步：** 从字符串 `A` 中选择子序列 `"AC"`，并将其追加到字符串 `C` 的末尾，即 `C = "ABAC"`。
> 现在，字符串 `C` 与字符串 `B` 相同，因此所需操作数为 2。

> **输入：** `A = "geeksforgeeks"`，`B = "programming"`
> **输出：** `-1`

## 方法

按照以下步骤解决这个问题：

1.  初始化一个映射，将字符串 `A` 中的字符映射到它们各自的索引。
2.  对于字符串 `A` 中的每个字符，记录其所有出现的情况。
3.  初始化一个变量，比如 `ans`，来存储所需操作的计数。由于操作次数必须大于 1，设置 `ans = 1`。
4.  遍历字符串 `B` 的字符，使用映射检查字符串 `A` 中是否存在该字符。
5.  最后，为每个操作最大化从字符串 `A` 中选择的子序列的长度。
6.  最后，打印所需的最少操作。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to count the minimum
// subsequences of a string A required
// to be appended to obtain the string B
void countminOpsToConstructAString(string A, string B)
{
    // Size of the string
    int N = A.length();
    int i = 0;

    // Maps characters to their
    // respective indices
    map<char, set<int>> mp;

    // Insert indices of characters
    // into the sets
    for (i = 0; i < N; i++) {
        mp[A[i]].insert(i);
    }

    // Stores the position of the last
    // visited index in the string A.
    // Initially set it to -1.
    int previous = -1;

    // Stores the required count
    int ans = 1;

    // Iterate over the characters of B
    for (i = 0; i < B.length(); i++) {
        char ch = B[i];

        // If the character in B is
        // not present in A, return -1
        if (mp[ch].size() == 0) {
            cout << -1;
            return;
        }

        // Fetch the next index from B[i]'s set
        auto it = mp[ch].upper_bound(previous);

        // If the iterator points to
        // the end of that set
        if (it == mp[ch].end()) {
            previous = -1;
            ans++;
            --i;
            continue;
        }

        // If it doesn't point to the
        // end, update previous
        previous = *it;
    }

    // Print the answer
    cout << ans;
}

// Driver Code
int main()
{
    string A = "abc", B = "abac";
    countminOpsToConstructAString(A, B);
    return 0;
}
```

## Python 3

```python
# Python3 program for the above approach
from bisect import bisect_right

# Function to count the minimum
# subsequences of a A required
# to be appended to obtain the B
def countminOpsToConstructAString(A, B):
    # Size of the string
    N = len(A)
    i = 0

    # Maps characters to their
    # respective indices
    mp = [[] for i in range(26)]

    # Insert indices of characters
    # into the sets
    for i in range(N):
        mp[ord(A[i]) - ord('a')].append(i)

    # Stores the position of the last
    # visited index in the A.
    # Initially set it to -1.
    previous = -1

    # Stores the required count
    ans, i = 1, 0

    # Iterate over the characters of B
    while i < len(B):
        ch = B[i]

        # If the character in B is
        # not present in A, return -1
        if (len(mp[ord(ch) - ord('a')]) == 0):
            print(-1)
            return

        # Fetch the next index from B[i]'s set
        it = bisect_right(mp[ord(ch) - ord('a')], previous)

        # If the iterator points to
        # the end of that set
        if (it == len(mp[ord(ch) - ord('a')])):
            previous = -1
            ans += 1
            # i -= 1
            continue

        # If it doesn't point to the
        # end, update previous
        previous = mp[ord(ch) - ord('a')][it]
        i += 1

    # Print answer
    print(ans)

# Driver Code
if __name__ == '__main__':
    A, B = "abc", "abac"
    countminOpsToConstructAString(A, B)

# This code is contributed by mohit kumar 29.
```

### Output

```
2
```

**时间复杂度：** `O(N * logN)`
**辅助空间：** `O(N)`