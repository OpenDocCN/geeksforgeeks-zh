# 使用多项式滚动散列函数对数组中的不同字符串进行计数

> 原文：[https://www.geeksforgeeks.org/count-distinct-strings-present-in-an-array-using-polynomial-rolling-hash-function/](https://www.geeksforgeeks.org/count-distinct-strings-present-in-an-array-using-polynomial-rolling-hash-function/)

给定一个字符串数组 `arr[]`，任务是使用[多项式滚动散列函数](https://www.geeksforgeeks.org/string-hashing-using-polynomial-rolling-hash-function/)找到数组中不同字符串的计数。

**示例：**

> **输入：** `arr[] = {"abcde", "abcce", "abcdf", "abcde", "abcdf"}`
> **输出：** 3
> **解释：**
> 数组中不同的字符串为 `{"abcde", "abcce", "abcdf"}`。
> 因此，要求的输出为 3。
>
> **输入：** `arr[] = {"ab", "abc", "abcd", "abcde", "a"}`
> **输出：** 5
> **解释：**
> 数组中不同的字符串是 `{"abcde", "abcd", "abc", "ab", "a"}`。
> 因此，要求输出为 5。

## 方法

使用[哈希](https://www.geeksforgeeks.org/hashing-data-structure/)可以解决问题。这个想法是使用[滚动散列函数](https://www.geeksforgeeks.org/string-hashing-using-polynomial-rolling-hash-function/)来计算数组中所有字符串的散列值，并将其存储在另一个数组中，比如 `Hash[]`。最后，打印 `Hash[]` 数组中不同元素的[计数](https://www.geeksforgeeks.org/count-distinct-elements-in-an-array/)。按照以下步骤解决问题：

*   初始化一个[数组](https://www.geeksforgeeks.org/vector-in-cpp-stl/)，比如 `Hash[]`，使用滚动哈希函数存储数组中所有字符串的哈希值。
*   初始化一个变量，比如 `cntElem`，来存储数组中不同字符串的计数。
*   [遍历数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/) `arr[]`。对于遇到的每个字符串，计算该字符串的哈希值，并将其存储在 `Hash[]` 数组中。
*   [排序数组](https://www.geeksforgeeks.org/sort-c-stl/) `Hash[]`。
*   [遍历数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/) `Hash[]`。对于每个数组元素，检查 `Hash[i]` 和 `Hash[i-1]` 是否相等。如果发现为假，则将 `cntElem` 增加 `1`。
*   最后，打印 `cntElem` 的值。

下面是上述方法的实现：

### C++

```cpp
// C++ program to implement
// the above approach

#include<bits/stdc++.h>
using namespace std;

// Function to find the hash value
// of a string
long long compute_hash(string str)
{

    int p = 31;
    int MOD = 1e9 + 7;
    long long hash_val = 0;
    long long mul = 1;

    // Traverse the string
    for (char ch : str) {

        // Update hash_val
        hash_val
            = (hash_val + (ch - 'a' + 1) * mul)
            % MOD;

        // Update mul
        mul = (mul * p) % MOD;
    }

    // Return hash_val of str
    return hash_val;
}

// Function to find the count of distinct
// strings present in the given array
int distinct_str(vector<string>& arr, int n)
{
    // Store the hash values of
    // the strings
    vector<long long> hash(n);

    // Traverse the array
    for (int i = 0; i < n; i++) {

        // Stores hash value of arr[i]
        hash[i] = compute_hash(arr[i]);
    }

    // Sort hash[] array
    sort(hash.begin(), hash.end());

    // Stores count of distinct
    // strings in the array
    int cntElem = 1;

    // Traverse hash[] array
    for (int i = 1; i < n; i++) {
        if (hash[i] != hash[i - 1]) {

            // Update cntElem
            cntElem++;
        }
    }

    return cntElem;
}

// Driver Code
int main()
{
    vector<string> arr={"abcde","abcce","abcdf","abcde"};

    int N = arr.size();

    cout << distinct_str(arr, N) << endl;

    return 0;
}
```

### Java

```java
// Java program to implement
// the above approach
import java.util.Arrays;

public class GFG {

    // Function to find the hash value
    // of a string
    static int compute_hash(String str)
    {

        int p = 31;
        int MOD = (int)1e9 + 7;
        int  hash_val = 0;
        int mul = 1;

        // Traverse the string
        for (int i = 0; i < str.length(); i++) {

            char ch = str.charAt(i);

            // Update hash_val
            hash_val
                = (hash_val + (ch - 'a' + 1) * mul)
                  % MOD;

            // Update mul
            mul = (mul * p) % MOD;
        }

        // Return hash_val of str
        return hash_val;
    }

    // Function to find the count of distinct
    // strings present in the given array
    static int distinct_str(String arr[], int n)
    {
        // Store the hash values of
        // the strings
        int hash[] = new int [n];

        // Traverse the array
        for (int i = 0; i < n; i++) {

            // Stores hash value of arr[i]
            hash[i] = compute_hash(arr[i]);
        }

        // Sort hash[] array
        Arrays.sort(hash);

        // Stores count of distinct
        // strings in the array
        int cntElem = 1;

        // Traverse hash[] array
        for (int i = 1; i < n; i++) {
            if (hash[i] != hash[i - 1]) {

                // Update cntElem
                cntElem++;
            }
        }

        return cntElem;
    }

    // Driver Code
    public static void main (String[] args)
    {
        String arr[] = { "abcde", "abcce",
                            "abcdf", "abcde" };

        int N = arr.length;

        System.out.println(distinct_str(arr, N));
    }
}

// This code is contributed by AnkThon
```

### Python 3

```python
# Python3 program to implement
# the above approach

# Function to find the hash value
# of a string
def compute_hash(str):

    p = 31
    MOD = 10**9 + 7
    hash_val = 0
    mul = 1

    # Traverse the string
    for ch in str:

        # Update hash_val
        hash_val = (hash_val + (ord(ch) - ord('a') + 1) * mul) % MOD

        # Update mul
        mul = (mul * p) % MOD

    # Return hash_val of str
    return hash_val

# Function to find the count of distinct
# strings present in the given array
def distinct_str(arr, n):

    # Store the hash values of
    # the strings
    hash = [0]*(n)

    # Traverse the array
    for i in range(n):

        # Stores hash value of arr[i]
        hash[i] = compute_hash(arr[i])

    # Sort hash[] array
    hash = sorted(hash)

    # Stores count of distinct
    # strings in the array
    cntElem = 1

    # Traverse hash[] array
    for i in range(1, n):
        if (hash[i] != hash[i - 1]):

            # Update cntElem
            cntElem += 1

    return cntElem

# Driver Code
if __name__ == '__main__':
    arr=["abcde", "abcce","abcdf", "abcde"]

    N = len(arr)

    print(distinct_str(arr, N))

# This code is contributed by mohit kumar 29
```

### C#

```csharp
// C# program to implement
// the above approach
using System;

class GFG
{

    // Function to find the hash value
    // of a string
    static int compute_hash(string str)
    {

        int p = 31;
        int MOD = (int)1e9 + 7;
        int  hash_val = 0;
        int mul = 1;

        // Traverse the string
        for (int i = 0; i < str.Length; i++)
        {
            char ch = str[i];

            // Update hash_val
            hash_val = (hash_val + (ch -
                        'a' + 1) * mul) % MOD;

            // Update mul
            mul = (mul * p) % MOD;
        }

        // Return hash_val of str
        return hash_val;
    }

    // Function to find the count of distinct
    // strings present in the given array
    static int distinct_str(string []arr, int n)
    {

        // Store the hash values of
        // the strings
        int []hash = new int [n];

        // Traverse the array
        for (int i = 0; i < n; i++)
        {

            // Stores hash value of arr[i]
            hash[i] = compute_hash(arr[i]);
        }

        // Sort hash[] array
        Array.Sort(hash);

        // Stores count of distinct
        // strings in the array
        int cntElem = 1;

        // Traverse hash[] array
        for (int i = 1; i < n; i++)
        {
            if (hash[i] != hash[i - 1])
            {

                // Update cntElem
                cntElem++;
            }
        }
        return cntElem;
    }

    // Driver Code
    public static void Main (String[] args)
    {
        string []arr = { "abcde", "abcce",
                            "abcdf", "abcde" };
        int N = arr.Length;
        Console.WriteLine(distinct_str(arr, N));
    }
}

// This code is contributed by AnkThon
```

## java 描述语言

```javascript
<script>
    // Javascript program to implement the above approach

    // Function to find the hash value
    // of a string
    function compute_hash(str)
    {

        let p = 31;
        let MOD = 1e9 + 7;
        let  hash_val = 0;
        let mul = 1;

        // Traverse the string
        for (let i = 0; i < str.length; i++)
        {   
            let ch = str[i];

            // Update hash_val
            hash_val = (hash_val + (ch.charCodeAt() - 'a'.charCodeAt() + 1) * mul) % MOD;

            // Update mul
            mul = (mul * p) % MOD;
        }

        // Return hash_val of str
        return hash_val;
    }

    // Function to find the count of distinct
    // strings present in the given array
    function distinct_str(arr, n)
    {

        // Store the hash values of
        // the strings
        let hash = new Array(n);

        // Traverse the array
        for (let i = 0; i < n; i++)
        {

            // Stores hash value of arr[i]
            hash[i] = compute_hash(arr[i]);
        }

        // Sort hash[] array
        hash.sort(function(a, b){return a - b});

        // Stores count of distinct
        // strings in the array
        let cntElem = 1;

        // Traverse hash[] array
        for (let i = 1; i < n; i++)
        {
            if (hash[i] != hash[i - 1])
            {

                // Update cntElem
                cntElem++;
            }
        }   
        return cntElem;
    }

    let arr = [ "abcde", "abcce", "abcdf", "abcde" ]; 
    let N = arr.length; 
    document.write(distinct_str(arr, N)); 

</script>
```

`Output:`

```

```

时间复杂度：`O(N * M)`，其中 `M` 为字符串的最大长度
辅助空间：`O(N)`