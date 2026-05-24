# 生成所有可能的字符串

> 原文: [https://www.geeksforgeeks.org/generate-all-possible-strings-formed-by-replacing-letters-with-given-respective-symbols/](https://www.geeksforgeeks.org/generate-all-possible-strings-formed-by-replacing-letters-with-given-respective-symbols/)

## 问题描述

给定由 `N` 个字符组成的字符串 `S` 和由多对字符组成的数组 `M[]`，使得字符串 `S` 中的任何字符 `M[i][0]` 都可以用字符 `M[i][1]` 替换，任务是生成通过用它们各自的字符替换字符串的一些字符而形成的所有可能的字符串。

**示例:**

> **输入:** `S = "aBc"`，`M = { 'a':'$', 'b':'#', 'c':'^' }`
> **输出:**
> ```
> aBc
> aB^
> a#c
> a#^
> $Bc
> $B^
> $#c
> $#^
> ```
>
> **输入:** `S = "a"`，`M = { 'a':'$' }`
> **输出:**
> ```
> a
> $
> ```

## 方法

给定的问题可以通过使用回溯来解决，通过用数组 `M[]` 中的映射字符替换每个字符来生成所有可能的字符串。按照以下步骤解决问题:

*   将数组 `M[]` 中所有映射的字符对存储在一张地图中，比如说 `map`。
*   定义一个递归函数比如 `generateLetters(S, P)`，其中 `S` 是修改后的字符串，`P` 是当前字符的索引:
    *   检查基本情况，即如果索引 `P` 等于 `N`，则打印字符串 `S` 并返回。
    *   不要改变当前字符和递归调用函数，`generateLetters(S, P + 1)`。
    *   现在，将字符 `S[P]` 替换为地图 `M` 中的相应符号，并调用函数 `generateLetters(S, P+1)`。
*   完成上述步骤后，调用函数 `generateLetters(S, 0)` 打印所有可能的字符串。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to generate all possible
// string by replacing the characters
// with mapped symbols
void generateLetters(string S, int P,
                     unordered_map<char, char> M)
{
    // Base Case
    if (P == S.size()) {
        cout << S << "\n";
        return;
    }

    // Function call with the P-th
    // character not replaced
    generateLetters(S, P + 1, M);

    // Replace the P-th character
    S[P] = M[S[P]];

    // Function call with the P-th
    // character replaced
    generateLetters(S, P + 1, M);

    return;
}

// Driver Code
int main()
{
    string S = "aBc";
    unordered_map<char, char> M;
    M['a'] = '$';
    M['B'] = '#';
    M['c'] = '^';
    M['d'] = '&';
    M['1'] = '*';
    M['2'] = '!';
    M['E'] = '@';

    // Function Call
    generateLetters(S, 0, M);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.HashMap;

class GFG{

// Function to generate all possible
// string by replacing the characters
// with mapped symbols
public static void generateLetters(String S, int P, HashMap<Character, Character> M)
{
    // Base Case
    if (P == S.length()) {
        System.out.println(S);
        return;
    }

    // Function call with the P-th
    // character not replaced
    generateLetters(S, P + 1, M);

    // Replace the P-th character
    S = S.substring(0, P) + M.get(S.charAt(P)) + S.substring(P + 1);

    // Function call with the P-th
    // character replaced
    generateLetters(S, P + 1, M);

    return;
}

// Driver Code
public static void main(String args[])
{
    String S = "aBc";
    HashMap<Character, Character> M = new HashMap<Character, Character>();
    M.put('a', '$');
    M.put('B', '#');
    M.put('c', '^');
    M.put('d', '&');
    M.put('1', '*');
    M.put('2', '!');
    M.put('E', '@');

    // Function Call
    generateLetters(S, 0, M);

}

}

// This code is contributed by _saurabh_jaiswal.
```

## Python 3

```python
# Python program for the above approach

# Function to generate all possible
# string by replacing the characters
# with mapped symbols
def generateLetters(S, P, M):

    # Base Case
    if (P == len(S)):
        print(S);
        return

    # Function call with the P-th
    # character not replaced
    generateLetters(S, P + 1, M);

    # Replace the P-th character
    S = S.replace(S[P], M[S[P]])

    # Function call with the P-th
    # character replaced
    generateLetters(S, P + 1, M);

# Driver Code
S = "aBc";
M = {};
M['a'] = '$';
M['B'] = '#'
M['c'] = '^'
M['d'] = '&'
M['1'] = '*'
M['2'] = '!'
M['E'] = '@'

# Function Call
generateLetters(S, 0, M);

# This code is contributed by _saurabh_jaiswal.
```

## C#

```csharp
// C# program for the above approach

using System;
using System.Collections.Generic;

class GFG{

// Function to generate all possible
// string by replacing the characters
// with mapped symbols
static void generateLetters(string S, int P,
                     Dictionary<char, char> M)
{
    // Base Case
    if (P == S.Length) {
        Console.WriteLine(S);
        return;
    }

    // Function call with the P-th
    // character not replaced
    generateLetters(S, P + 1, M);

    // Replace the P-th character
   S = S.Substring(0, P) + M[S[P]] + S.Substring(P + 1);

    // Function call with the P-th
    // character replaced
    generateLetters(S, P + 1, M);

    return;
}

// Driver Code
public static void Main()
{
    string S = "aBc";
    Dictionary<char, char> M = new Dictionary<char,char>();
    M.Add('a','$');
    M.Add('B','#');
    M.Add('c','^');
    M.Add('d','&');
    M.Add('1','*');
    M.Add('2','!');
    M.Add('E','@');

    // Function Call
    generateLetters(S, 0, M);

}
}

// This code is contributed by SURENDRA_GANGWAR.
```

## JavaScript

```javascript
<script>

// JavaScript program for the above approach

// Function to generate all possible
// string by replacing the characters
// with mapped symbols
function generateLetters(S, P, M)
{

    // Base Case
    if (P == S.length)
    {
        document.write(S + "<br>");
        return;
    }

    // Function call with the P-th
    // character not replaced
    generateLetters(S, P + 1, M);

    // Replace the P-th character
    S = S.replace(S.charAt(P), M.get(S[P]))

    // Function call with the P-th
    // character replaced
    generateLetters(S, P + 1, M);
    return;
}

// Driver Code
let S = "aBc";
let M = new Map();
M.set('a', '$');
M.set('B', '#');
M.set('c', '^');
M.set('d', '&');
M.set('1', '*');
M.set('2', '!');
M.set('E', '@');

// Function Call
generateLetters(S, 0, M);

// This code is contributed by Potta Lokesh

</script>
```

**输出:**

```
aBc
aB^
a#c
a#^
$Bc
$B^
$#c
$#^
```

**时间复杂度:** `O(N * 2^N)`
**辅助空间:** `O(1)`