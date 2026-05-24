# 用乘积 K 生成最长可能的数组，这样每个数组元素都可以被它之前的相邻元素整除

> 原文: [https://www.geeksforgeeks.org/generate-longest-possible-array-with-product-k-such-that-each-array-element-is-divisible-by-its-previous-adjacent-element/](https://www.geeksforgeeks.org/generate-longest-possible-array-with-product-k-such-that-each-array-element-is-divisible-by-its-previous-adjacent-element/)

给定一个整数 `K`，任务是构造一个最大长度的数组，所有数组元素的乘积等于 `K`，这样除了第一个数组元素之外的每个数组元素都可以被它的前一个相邻元素整除。
> 注意: 生成数组中的每个数组元素必须大于 1。

## 示例

> **输入**: `K = 4`
> **输出**: `{2, 2}`
> **解释**:
> 第二个元素，即 `arr[1]` (= 2) 可被第一个元素即 `arr[0]` (= 2) 整除。
> 数组元素的乘积 = 2 * 2 = 4 (= `K`)。
> 因此，数组满足要求的条件。

> **输入**: `K = 23`
> **输出**: `{23}`

## 方法

解决这个问题的思路是找到 `K` 的所有质因数及其各自的幂:
> 质因数[1] <sup>x</sup> * 质因数[2] <sup>y</sup> * ... * 质因数[i] <sup>z</sup> = `K`

按照以下步骤解决此问题:
*   找到质因数，记为 `X`，其幂最大，记为 `Y`。
*   然后，`Y` 将是所需数组的长度。
*   因此，构造一个长度为 `Y` 的数组，其中所有元素等于 `X`。
*   要使数组的乘积等于 `K`，将最后一个元素乘以 `K / X^y`。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to construct longest array
// with product K such that each element
// is divisible by its previous element
void findLongestArray(int K)
{
    // Stores the prime factors of K
    vector<pair<int, int> > primefactors;

    int K_temp = K;

    for (int i = 2; i * i <= K; i++) {

        // Stores the power to which
        // primefactor i is raised
        int count = 0;

        while (K_temp % i == 0) {
            K_temp /= i;
            count++;
        }

        if (count > 0)
            primefactors.push_back({ count, i });
    }

    if (K_temp != 1)
        primefactors.push_back(
            { 1, K_temp });

    // Sort prime factors in descending order
    sort(primefactors.rbegin(),
         primefactors.rend());

    // Stores the final array
    vector<int> answer(
        primefactors[0].first,
        primefactors[0].second);

    // Multiply the last element by K
    answer.back() *= K;

    for (int i = 0;
         i < primefactors[0].first; i++) {
        answer.back() /= primefactors[0].second;
    }

    // Print the constructed array
    cout << "{";
    for (int i = 0; i < (int)answer.size(); i++) {
        if (i == answer.size() - 1)
            cout << answer[i] << "}";
        else
            cout << answer[i] << ", ";
    }
}

// Driver Code
int main()
{
    int K = 4;
    findLongestArray(K);
}
```

## Java

```java
// java program for the above approach
import java.io.*;
import java.lang.*;
import java.util.*;

class GFG {

    // Function to construct longest array
    // with product K such that each element
    // is divisible by its previous element
    static void findLongestArray(int K)
    {
        // Stores the prime factors of K
        ArrayList<int[]> primefactors = new ArrayList<>();

        int K_temp = K;

        for (int i = 2; i * i <= K; i++) {

            // Stores the power to which
            // primefactor i is raised
            int count = 0;

            while (K_temp % i == 0) {
                K_temp /= i;
                count++;
            }

            if (count > 0)
                primefactors.add(new int[] { count, i });
        }

        if (K_temp != 1)
            primefactors.add(new int[] { 1, K_temp });

        // Sort prime factors in descending order
        Collections.sort(primefactors, (x, y) -> {
            if (x[0] != y[0])
                return y[0] - x[0];
            return y[1] - x[1];
        });

        // Stores the final array
        int n = primefactors.get(0)[0];
        int val = primefactors.get(0)[1];
        int answer[] = new int[n];
        Arrays.fill(answer, val);

        // Multiply the last element by K
        answer[n - 1] *= K;

        for (int i = 0; i < n; i++) {
            answer[n - 1] /= val;
        }

        // Print the constructed array
        System.out.print("{");
        for (int i = 0; i < answer.length; i++) {
            if (i == answer.length - 1)
                System.out.print(answer[i] + "}");
            else
                System.out.print(answer[i] + ", ");
        }
    }

    // Driver Code
    public static void main(String[] args)
    {

        int K = 4;
        findLongestArray(K);
    }
}

// This code is contributed by Kingash.
```

## Python 3

```python
# Python 3 program for the above approach

# Function to construct longest array
# with product K such that each element
# is divisible by its previous element
def findLongestArray(K):

    # Stores the prime factors of K
    primefactors = []

    K_temp = K

    i = 2
    while i * i <= K:

        # Stores the power to which
        # primefactor i is raised
        count = 0

        while (K_temp % i == 0):
            K_temp //= i
            count += 1

        if (count > 0):
            primefactors.append([count, i])

        i += 1

    if (K_temp != 1):
        primefactors.append(
            [1, K_temp])

    # Sort prime factors in descending order
    primefactors.sort()

    # Stores the final array
    answer = [primefactors[0][0],
              primefactors[0][1]]

    # Multiply the last element by K
    answer[-1] *= K

    for i in range(primefactors[0][0]):
        answer[-1] //= primefactors[0][1]

    # Print the constructed array
    print("{", end = "")
    for i in range(len(answer)):
        if (i == len(answer) - 1):
            print(answer[i], end = "}")
        else:
            print(answer[i], end = ", ")

# Driver Code
if __name__ == "__main__":
    K = 4
    findLongestArray(K)

    # This code is contributed by ukasp.
```

## JavaScript

```javascript
<script>

// JavaScript program for the above approach

// Function to construct longest array
    // with product K such that each element
    // is divisible by its previous element
function findLongestArray(K)
{
    // Stores the prime factors of K
        let primefactors = [];

        let K_temp = K;

        for (let i = 2; i * i <= K; i++) {

            // Stores the power to which
            // primefactor i is raised
            let count = 0;

            while (K_temp % i == 0) {
                K_temp = Math.floor(K_temp/i);
                count++;
            }

            if (count > 0)
                primefactors.push([ count, i ]);
        }

        if (K_temp != 1)
            primefactors.push([ 1, K_temp ]);

        // Sort prime factors in descending order
        primefactors.sort(function(x, y) {
            if (x[0] != y[0])
                return y[0] - x[0];
            return y[1] - x[1];
        });

        // Stores the final array
        let n = primefactors[0][0];
        let val = primefactors[0][1];
        let answer = new Array(n);
        for(let i=0;i<n;i++)
        {
            answer[i]=val;
        }

        // Multiply the last element by K
        answer[n - 1] *= K;

        for (let i = 0; i < n; i++) {
            answer[n - 1] = Math.floor(answer[n - 1]/val);
        }

        // Print the constructed array
        document.write("{");
        for (let i = 0; i < answer.length; i++) {
            if (i == answer.length - 1)
                document.write(answer[i] + "}");
            else
                document.write(answer[i] + ", ");
        }
}

// Driver Code
let K = 4;
findLongestArray(K);

// This code is contributed by avanitrachhadiya2155

</script>
```

## 输出

```
{2, 2}
```

## 复杂度分析

*   **时间复杂度:** `O(√(K) * log(√(K)))`
*   **辅助空间:** `O(√(K))`