# 统计首字符为辅音且无相邻辅音或元音对的字谜数量

> 原文：[https://www.geeksforgeeks.org/count-anagrams-having-first-character-as-a-consonant-and-no-pair-of-consonants-or-vowels-placed-adjacently/](https://www.geeksforgeeks.org/count-anagrams-having-first-character-as-a-consonant-and-no-pair-of-consonants-or-vowels-placed-adjacently/)

给定一个长度为 `N` 的字符串 `S`，任务是统计 `S` 的字谜中，满足第一个字符为辅音且没有一对辅音或元音相邻的数量。

**示例：**

> **输入：** `S = "GADO"`
> **输出：** 4
> **说明：**
> 满足给定条件的字符串 `S` 的字谜是 `GADO`、`GODA`、`DOGA`、`DAGO`。
> 所以这样的字谜总数是 4 个。
>
> **输入：** `S = "AABCY"`
> **输出：** 6
> **说明：**
> 满足给定条件的字符串 `S` 的字谜是 `BACAY`、`BAYAC`、`CABAY`、`CAYAB`、`YABAC`、`YACAB`。
> 因此，这样的字谜总数为 6 个。

**朴素方法：** 最简单的方法是生成给定字符串的所有可能的字谜，并对那些满足给定条件的字谜进行计数。最后，打印获得的计数。
**时间复杂度：** `O(N! * N)`
**辅助空间：** `O(1)`

**高效方法：** 上述方法也可以基于以下观察进行优化：

*   辅音和元音数量相等的字符串满足给定条件。
*   辅音多于元音的字符串也满足给定条件。
*   除了这两个条件，可能的字谜计数永远是 `0`。
*   现在，这个问题可以通过使用组合公式来解决。假设有 `C1`、`C2`……、`CN` 个辅音和 `V1`、`V2`……、`VN` 个元音在字符串 `S` 中，`ΣC` 和 `ΣV` 分别表示辅音和元音的总数，那么答案应该是：

> `(ΣC! * ΣV!) / ((C1! * C2! * ... * CN!) * (V1! * V2! * ... * VN!))`
>
> 其中，
> `Ci` 是第 `i` 种辅音的个数。
> `Vi` 是第 `i` 种元音的个数。

按照以下步骤解决问题：

*   初始化一个变量，例如 `ans`，存储字谜总数。
*   将字符串 `S` 每个字符的频率存储在哈希表 `count` 中。
*   将 `S` 中的元音和辅音的个数分别存储在变量 `v` 和 `c` 中。
*   如果 `v` 的值不等于 `c` 或 `c` 不等于 `(v + 1)`，则打印 `0`。否则，执行以下步骤：
    *   将 `denominator` 初始化为 `1`。
    *   使用变量 `i` 遍历字符串 `S`，并将 `denominator` 更新为 `denominator * (count[S[i]])!`。
    *   将 `numerator` 初始化为 `v! * c!`，将 `ans` 的值更新为 `numerator / denominator`。
*   完成以上步骤后，打印 `ans` 的值作为结果。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>

#define ll long long
#define mod 1000000007
#define N 1000001
using namespace std;

// Function to compute factorials till N
void Precomputefact(unordered_map<ll, ll>& fac)
{
    ll ans = 1;

    // Iterate in the range [1, N]
    for (ll i = 1; i <= N; i++) {

        // Update ans to ans*i
        ans = (ans * i) % mod;

        // Store the value of ans
        // in fac[i]
        fac[i] = ans;
    }
    return;
}

// Function to check whether the
// current character is a vowel or not
bool isVowel(char a)
{
    if (a == 'A' || a == 'E' || a == 'I' || a == 'O'
        || a == 'U')
        return true;
    else
        return false;
}

// Function to count the number of
// anagrams of S satisfying the
// given condition
void countAnagrams(string s, int n)
{
    // Store the factorials upto N
    unordered_map<ll, ll> fac;

    // Function Call to generate
    // all factorials upto n
    Precomputefact(fac);

    // Create a hashmap to store
    // frequencies of all characters
    unordered_map<char, ll> count;

    // Store the count of
    // vowels and consonants
    int vo = 0, co = 0;

    // Iterate through all
    // characters in the string
    for (int i = 0; i < n; i++) {

        // Update the frequency
        // of current character
        count[s[i]]++;

        // Check if the character
        // is vowel or consonant
        if (isVowel(s[i]))
            vo++;
        else
            co++;
    }

    // Check if ΣC==ΣV+1 or ΣC==ΣV
    if ((co == vo + 1) || (co == vo)) {

        // Store the denominator
        ll deno = 1;

        // Calculate the denominator
        // of the expression
        for (auto c : count) {

            // Multiply denominator by factorial
            // of counts of all letters
            deno = (deno * fac[c.second]) % mod;
        }

        // Store the numerator
        ll nume = fac[co] % mod;
        nume = (nume * fac[vo]) % mod;

        // Store the answer by dividing
        // numerator by denominator
        ll ans = nume / deno;

        // Print the answer
        cout << ans;
    }

    // Otherwise, print 0
    else {
        cout << 0;
    }
}

// Driver Code
int main()
{
    string S = "GADO";
    int l = S.size();
    countAnagrams(S, l);

    return 0;
}
```

## Python 3

```python
# Python 3 program for the above approach

mod = 1000000007
N = 1000001

fac = {}

# Function to compute factorials till N
def Precomputefact():
    global fac
    ans = 1

    # Iterate in the range [1, N]
    for i in range(1, N + 1, 1):
        # Update ans to ans*i
        ans = (ans * i) % mod

        # Store the value of ans
        # in fac[i]
        fac[i] = ans

    return

# Function to check whether the
# current character is a vowel or not
def isVowel(a):
    if (a == 'A' or a == 'E' or a == 'I' or a == 'O' or a == 'U'):
        return True
    else:
        return False

# Function to count the number of
# anagrams of S satisfying the
# given condition
def countAnagrams(s, n):
    # Store the factorials upto N
    global fac

    # Function Call to generate
    # all factorials upto n
    Precomputefact()

    # Create a hashmap to store
    # frequencies of all characters
    count = {}

    # Store the count of
    # vowels and consonants
    vo = 0
    co = 0

    # Iterate through all
    # characters in the string
    for i in range(n):
        # Update the frequency
        # of current character
        if s[i] in count:
            count[s[i]] += 1
        else:
            count[s[i]] = 1

        # Check if the character
        # is vowel or consonant
        if (isVowel(s[i])):
            vo += 1
        else:
            co += 1

    # Check if ΣC==ΣV+1 or ΣC==ΣV
    if ((co == vo + 1) or (co == vo)):
        # Store the denominator
        deno = 1

        # Calculate the denominator
        # of the expression
        for key, value in count.items():
            # Multiply denominator by factorial
            # of counts of all letters
            deno = (deno * fac[value]) % mod

        # Store the numerator
        nume = fac[co] % mod
        nume = (nume * fac[vo]) % mod

        # Store the answer by dividing
        # numerator by denominator
        ans = nume // deno

        # Print the answer
        print(ans)

    # Otherwise, print 0
    else:
        print(0)

# Driver Code
if __name__ == '__main__':
    S = "GADO"
    l = len(S)
    countAnagrams(S, l)

# This code is contributed by ipg2016107.
```

**输出：**

```
4
```

**时间复杂度：** `O(N)`
**辅助空间：** `O(N)`