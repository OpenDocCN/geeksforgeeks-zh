# 检查一个数字串是否可以被分割成连续数字之间的差值等于 K 的子串

> 原文: [https://www.geeksforgeeks.org/check-if-a-numeric-string-can-be-split-into-substrings-having-difference-between-consecutive-numbers-equal-to-k/](https://www.geeksforgeeks.org/check-if-a-numeric-string-can-be-split-into-substrings-having-difference-between-consecutive-numbers-equal-to-k/)

给定一个由 `N` 位和一个正整数 `K` 组成的数字字符串 `S`，任务是检查给定的字符串是否可以拆分成多个子字符串，并且连续子字符串之间的差值等于 `K`。

## 示例

> **输入:** `S = "8642"`，`K = 2`
> **输出:** 是
> **解释:** 将给定字符串拆分为 `{"8", "6", "4", "2"}`。现在，连续子串之间的差值是 `K(= 2)`。

> **输入:** `S = "1009896"`，`K = 0`
> **输出:** 否

## 方法

给定的问题可以通过生成给定字符串的所有可能的子串，并检查生成的子串的任意子集的连接是否等于给定的字符串 `S`，并且作为子串的数字的连续差为 `K`，然后打印“是”。否则，打印“否”。按照以下步骤解决问题：

*   使用变量 `i` 迭代范围 `[1, N/2]`，并执行以下步骤:
    *   将长度为 `i` 的子串从 `0` 开始存储在变量 `X` 中。
    *   生成大小为 `N` 的序列，从这个数字 `X` 开始，其中连续项的差值为 `K`。将该字符串存储在变量 `test` 中。
    *   如果两个字符串 `test` 和 `S` 相等，则将 `ans` 的值更新为 `true` 和跳出循环。
*   完成以上步骤后，如果 `ans` 的值为 `false`，则打印“否”。否则，打印“是”。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to check if a numeric string
// can be split into substrings such that
// the difference between the consecutive
// substrings is K
void isPossible(string s, int K)
{
    bool valid = false;
    long firstx = -1;

    // Stores the size of the string
    int n = s.length();

    // Iterate over the range [1, N] and
    // try each possible starting number
    for (int i = 1; i <= n / 2; ++i) {

        long x = stol(s.substr(0, i));
        firstx = x;

        // Convert the number to string
        string test = to_string(x);

        // Build up a sequence
        // starting with the number
        while (test.length() < s.length()) {
            x -= K;
            test += to_string(x);
        }

        // Compare it with the
        // original string s
        if (test == s) {
            valid = true;
            break;
        }
    }

    // Print the result
    cout << ((valid == true) ? "Yes " : "No");
}

// Driver Code
int main()
{
    string S = "8642";
    int K = 2;
    isPossible(S, K);

    return 0;
}
```

## Python 3

```python
# python 3 program for the above approach

# Function to check if a numeric string
# can be split into substrings such that
# the difference between the consecutive
# substrings is K
def isPossible(s, K):
    valid = False
    firstx = -1

    # Stores the size of the string
    n = len(s)

    # Iterate over the range [1, N] and
    # try each possible starting number
    for i in range(1, n // 2 + 1, 1):
        x = int(s[0:i])
        firstx = x

        # Convert the number to string
        test = str(x)

        # Build up a sequence
        # starting with the number
        while (len(test) < len(s)):
            x -= K
            test += str(x)

        # Compare it with the
        # original string s
        if (test == s):
            valid = True
            break

    # Print the result
    print("Yes") if valid == True else print("No")

# Driver Code
if __name__ == '__main__':
    S = "8642"
    K = 2
    isPossible(S, K)

# This code is contributed by ipg2016107.
```

## JavaScript

```javascript
// JavaScript program for the above approach

// Function to check if a numeric string
// can be split into substrings such that
// the difference between the consecutive
// substrings is K
function isPossible(s, K)
{
    let valid = false;
    let firstx = -1;

    // Stores the size of the string
    let n = s.length;

    // Iterate over the range [1, N] and
    // try each possible starting number
    for (let i = 1; i <= n / 2; ++i) {

        let x = (s.substr(0, i));
        firstx = x;

        // Convert the number to string
        let test = x.toString();

        // Build up a sequence
        // starting with the number
        while (test.length < s.length) {
            x -= K;
            test += x.toString();
        }

        // Compare it with the
        // original string s
        if (test == s) {
            valid = true;
            break;
        }
    }

    // Print the result
    document.write((valid == true) ? "Yes " : "No");
}

// Driver Code
let S = "8642";
let K = 2;
isPossible(S, K);
```

**输出:**

```
Yes
```

**时间复杂度:** `O(N^2)`
**辅助空间:** `O(N)`