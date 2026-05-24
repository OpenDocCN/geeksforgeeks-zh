# 通过插入字符修改字符串，使得每个 K 长度的子串仅由唯一的字符组成

> 原文: [https://www.geeksforgeeks.org/modify-string-by-inserting-characters-such-that-every-k-length-substring-consists-of-unique-characters-only/](https://www.geeksforgeeks.org/modify-string-by-inserting-characters-such-that-every-k-length-substring-consists-of-unique-characters-only/)

给定大小为 `N` 的字符串 `S`，由 `K` 不同的字符和 `(N–K)` 个 `'?'` 组成，任务是替换所有 `'?'` 字符串中的现有字符，使得大小为 `K` 的每个子字符串仅由唯一字符组成。如果不可能，则打印 `-1`。

## 示例

**输入:** `S = "????abcd"`，`K = 4`
**输出:** `abcdabcd`
**解释:**
替换 4 个 `'?'` 为 `"abcd"` 的 `S` 将字符串 `S` 修改为 `"abcdabcd"`，满足给定条件。

**输入:** `S = "?a?b?c"`，`K = 3`
**输出:** `bacbac`
**解释:**
将 `S[0]` 替换为 `'b'`，`S[2]` 替换为 `'c'`，`S[4]` 替换为 `'a'`，将字符串 `S` 修改为 `"bacbac"`，满足给定条件。

## 方法

这个想法是基于这样的观察：在最终的结果字符串中，每个字符必须出现在恰好 `K` 个位置之后，就像第 `(K + 1)` 个字符必须与第 `1` 个字符相同，第 `(K + 2)` 个字符必须与第 `2` 个字符相同。

按照以下步骤解决问题:

1.  初始化一个 hashmap `M` 来存储字符的位置。
2.  使用变量 `i` 遍历字符串 `S`，如果当前字符 `S[i]` 与 `'?'` 不相同，然后更新 `M[i % K] = S[i]`。
3.  使用变量 `i` 遍历字符串 `S`，如果 `i%k` 的值在地图 `M` 中不存在，则打印 `-1` 并跳出循环。否则将 `S[i]` 更新为 `M[i % K]`。
4.  完成上述步骤后，如果循环没有中断，则打印 `S` 作为结果字符串。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to replace all '?'
// characters in a string such
// that the given conditions are satisfied
void fillString(string s, int k)
{
    unordered_map<int, char> mp;

    // Traverse the string to Map the
    // characters with respective positions
    for (int i = 0; i < s.size(); i++) {
        if (s[i] != '?') {
            mp[i % k] = s[i];
        }
    }

    // Traverse the string again and
    // replace all unknown characters
    for (int i = 0; i < s.size(); i++) {

        // If i % k is not found in
        // the Map M, then return -1
        if (mp.find(i % k) == mp.end()) {

            cout << -1;
            return;
        }

        // Update S[i]
        s[i] = mp[i % k];
    }

    // Print the string S
    cout << s;
}

// Driver Code
int main()
{
    string S = "????abcd";
    int K = 4;
    fillString(S, K);

    return 0;
}
```

## Java

```java
// Java Program to implement
// the above approach
import java.io.*;
import java.util.*;

class GFG {

    // Function to replace all '?'
    // characters in a string such
    // that the given conditions are satisfied
    static void fillString(String str, int k)
    {

        char s[] = str.toCharArray();

        HashMap<Integer, Character> mp = new HashMap<>();

        // Traverse the string to Map the
        // characters with respective positions
        for (int i = 0; i < s.length; i++) {
            if (s[i] != '?') {
                mp.put(i % k, s[i]);
            }
        }

        // Traverse the string again and
        // replace all unknown characters
        for (int i = 0; i < s.length; i++) {

            // If i % k is not found in
            // the Map M, then return -1
            if (!mp.containsKey(i % k)) {
                System.out.println(-1);
                return;
            }

            // Update S[i]
            s[i] = mp.getOrDefault(i % k, s[i]);
        }

        // Print the string S
        System.out.println(new String(s));
    }

    // Driver Code
    public static void main(String[] args)
    {

        String S = "????abcd";
        int K = 4;
        fillString(S, K);
    }
}

// This code is contributed by Kingash.
```

## Python 3

```python
# Python 3 program for the above approach

# Function to replace all '?'
# characters in a string such
# that the given conditions are satisfied
def fillString(s, k):
    mp = {}

    # Traverse the string to Map the
    # characters with respective positions
    for i in range(len(s)):
        if (s[i] != '?'):
            mp[i % k] = s[i]

    # Traverse the string again and
    # replace all unknown characters
    s = list(s)
    for i in range(len(s)):

        # If i % k is not found in
        # the Map M, then return -1
        if ((i % k) not in mp):
            print(-1)
            return

        # Update S[i]
        s[i] = mp[i % k]

    # Print the string S
    s = ''.join(s)
    print(s)

# Driver Code
if __name__ == '__main__':
    S = "????abcd"
    K = 4
    fillString(S, K)

    # This code is contributed by bgangwar59.
```

## C#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;

class GFG
{

  // Function to replace all '?'
  // characters in a string such
  // that the given conditions are satisfied
  static void fillString(string str, int k)
  {

    char[] s = str.ToCharArray();

    Dictionary<int,
    int> mp = new Dictionary<int,
    int>();

    // Traverse the string to Map the
    // characters with respective positions
    for (int i = 0; i < s.Length; i++) {
      if (s[i] != '?') {
        mp[i % k] = s[i];
      }
    }

    // Traverse the string again and
    // replace all unknown characters
    for (int i = 0; i < s.Length; i++) {

      // If i % k is not found in
      // the Map M, then return -1
      if (!mp.ContainsKey(i % k)) {
        Console.WriteLine(-1);
        return;
      }

      // Update S[i]
      s[i] = (char)mp[i % k];

    }

    // Print the string S
    Console.WriteLine(new string(s));
  }

  // Driver code
  static void Main()
  {
    string S = "????abcd";
    int K = 4;
    fillString(S, K);
  }
}

// This code is contributed by susmitakundugoaldanga.
```

## JavaScript

```javascript
<script>
      // JavaScript program for the above approach
      // Function to replace all '?'
      // characters in a string such
      // that the given conditions are satisfied
      function fillString(str, k) {
        var s = str.split("");

        var mp = {};

        // Traverse the string to Map the
        // characters with respective positions
        for (var i = 0; i < s.length; i++) {
          if (s[i] !== "?") {
            mp[i % k] = s[i];
          }
        }

        // Traverse the string again and
        // replace all unknown characters
        for (var i = 0; i < s.length; i++) {
          // If i % k is not found in
          // the Map M, then return -1
          if (!mp.hasOwnProperty(i % k)) {
            document.write(-1);
            return;
          }

          // Update S[i]
          s[i] = mp[i % k];
        }

        // Print the string S
        document.write(s.join("") + "<br>");
      }

      // Driver code
      var S = "????abcd";
      var K = 4;
      fillString(S, K);
    </script>
```

**输出:**

```
abcdabcd
```

时间复杂度: `O(N)`
辅助空间: `O(N)`