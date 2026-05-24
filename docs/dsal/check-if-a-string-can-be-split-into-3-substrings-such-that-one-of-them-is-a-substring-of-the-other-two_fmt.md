# 检查一个字符串是否可以拆分成 3 个子字符串，其中一个是另外两个的子字符串

> 原文: [https://www.geeksforgeeks.org/check-if-a-string-can-be-split-into-3-substrings-such-that-one-of-them-is-a-substring-of-the-other-two/](https://www.geeksforgeeks.org/check-if-a-string-can-be-split-into-3-substrings-such-that-one-of-them-is-a-substring-of-the-other-two/)

给定由 **N** 个小写字母组成的字符串 **S**，任务是检查是否有可能将字符串 **S** 拆分为三个非空子字符串，使得 **Y** 是字符串 **X** 和 **Z** 的子字符串。如果可以拆分字符串 **S**，则打印`“是”`。否则，打印`“否”`。

**示例:**

> **输入:** `S = "geekseekforgeeks"`
> **输出:** 是
> **解释:**
> 给定的字符串 `S = "geekseekforgeeks"` 可以拆分为 `X = "geeks"`、`Y = "eek"` 和 `Z = "forgeeks"`。
> 字符串 `Y` 是字符串 `X` 和 `Z` 的子字符串。
>
> **输入:** `S = "naturalxws"`
> **输出:** 否

**方法:** 给定的问题可以通过存储唯一字符的频率来解决，观察如果存在任何具有频率**至少有 3 个**的字符，那么字符串可以被分割成满足给定条件的 3 个子串。按照以下步骤解决问题:

*   初始化一个数组，比如`hash[]`，来存储字符串 **S** 中字符的频率。
*   迭代字符串的字符，并将字符串中出现的每个字符的频率 **S** 存储在数组`hash[]`中。
*   遍历数组`hash[]`，如果任意字符的出现频率大于 **2**，则打印`“是”`并跳出循环。
*   完成上述步骤后，如果不存在频率**至少为 3** 的字符，则打印`“否”`。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to check if string S contains
// any character with frequency >= 3 or not
string freqCheck(string S, int N)
{
    // Stores frequency of characters
    int hash[26] = { 0 };

    // Iterate over the string
    for (int i = 0; i < N; i++) {

        // Update the frequency
        // of current character
        hash[S[i] - 'a']++;
    }

    // Iterate over the hash array
    for (int i = 0; i < 26; i++) {

        // If any character has
        // frequency >= 3
        if (hash[i] > 2) {
            return "Yes";
        }
    }

    // Otherwise
    return "No";
}

// Driver Code
int main()
{
    string S = "geekseekforgeeks";
    int N = S.length();
    cout << freqCheck(S, N);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.io.*;
import java.lang.*;
import java.util.*;

class GFG{

// Function to check if string S contains
// any character with frequency >= 3 or not
static String freqCheck(String S, int N)
{

    // Stores frequency of characters
    int hash[] = new int[26];

    // Iterate over the string
    for(int i = 0; i < N; i++)
    {

        // Update the frequency
        // of current character
        hash[S.charAt(i) - 'a']++;
    }

    // Iterate over the hash array
    for(int i = 0; i < 26; i++)
    {

        // If any character has
        // frequency >= 3
        if (hash[i] > 2)
        {
            return "Yes";
        }
    }

    // Otherwise
    return "No";
}

// Driver Code
public static void main(String[] args)
{
    String S = "geekseekforgeeks";
    int N = S.length();

    System.out.println(freqCheck(S, N));
}
}

// This code is contributed by Kingash
```

## Python 3

```python
# Python3 program for the above approach

# Function to check if string S contains
# any character with frequency >= 3 or not
def freqCheck(S, N):

    # Stores frequency of characters
    hash = [0] * 26

    # Iterate over the string
    for i in range(N):

        # Update the frequency
        # of current character
        hash[ord(S[i]) - ord('a')] += 1

    # Iterate over the hash array
    for i in range(26):

        # If any character has
        # frequency >= 3
        if (hash[i] > 2):
            return "Yes"

    # Otherwise
    return "No"

# Driver Code
if __name__ == "__main__":

    S = "geekseekforgeeks"
    N = len(S)

    print(freqCheck(S, N))

# This code is contributed by ukasp
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to check if string S contains
// any character with frequency >= 3 or not
static string freqCheck(string S, int N)
{

    // Stores frequency of characters
    int[] hash = new int[26];

    // Iterate over the string
    for(int i = 0; i < N; i++)
    {

        // Update the frequency
        // of current character
        hash[S[i] - 'a']++;
    }

    // Iterate over the hash array
    for(int i = 0; i < 26; i++)
    {

        // If any character has
        // frequency >= 3
        if (hash[i] > 2)
        {
            return "Yes";
        }
    }

    // Otherwise
    return "No";
}

// Driver code
static public void Main()
{
    string S = "geekseekforgeeks";
    int N = S.Length;

    Console.WriteLine(freqCheck(S, N));
}
}

// This code is contributed by offbeat
```

## JavaScript

```javascript
<script>
    // Javascript program for the above approach

// Function to check if string S contains
// any character with frequency >= 3 or not
function freqCheck(S, N){

    // Stores frequency of characters
    let hash = new Array(26).fill(0)

    // Iterate over the string
    for(let i = 0; i < N; i++){

        // Update the frequency
        // of current character
        hash[S.charCodeAt(i) - 'a'.charCodeAt(0)] += 1
    }
    // Iterate over the hash array
    for(let i = 0; i < 26; i++){

        // If any character has
        // frequency >= 3
        if (hash[i] > 2){
            return "Yes"
        }
    }

    // Otherwise
    return "No"
}
// Driver Code

    let S = "geekseekforgeeks"
    let N = S.length

    document.write(freqCheck(S, N))

// This code is contributed by gfgking
</script>
```

**输出:**

```
Yes
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`