# 两个数组中满足给定条件的字符串数

> 原文: [https://www.geeksforgeeks.org/number-of-strings-in-two-array-satisfy-the-given-conditions/](https://www.geeksforgeeks.org/number-of-strings-in-two-array-satisfy-the-given-conditions/)

给定两个字符串数组 `arr1[]` 和 `arr2[]`。对于 `arr2[]` (记为 `str2`) 中的每一个字符串，任务是统计 `arr1[]` (记为 `str1`) 中满足以下条件的字符串数量:
*   `str1` 和 `str2` 的第一个字符必须相等。
*   字符串 `str2` 必须包含字符串 `str1` 的每个字符。

**示例:**

> **输入:** `arr1[] = {"aaaa", "as", "able", "ability", "actt", "actor", "access"}`, `arr2[] = {"aboveyz", "abrodyz", "absoryz", "actresz", "gaswxyz"}`
> **输出:**
> 1
> 3
> 2
> 4
> 0
> **解释:**
> 以下是 `arr1[]` 中的字符串，如下
> 1 个表示 "aboveyz" 的有效词: "aaaa"。
> 3 个表示 "abrodyz" 的有效词: "aaaa", "as", "able"。
> 2 个对 "absoryz" 有效的词: "aaaa", "as"。
> 4 个 "actresz" 的有效词: "aaaa", "as", "actt", "access"。
> 没有 "gaswxyz" 的有效单词，因为列表中没有包含字母 "g" 的单词。

> **输入:** `arr1[] = {"abbg", "able", "absolute", "abil", "actresz", "gaswxyz"}`, `arr2[] = {"abbgaaa", "asas", "able", "ability"}`
> **输出:**
> 1
> 0
> 1
> 1

**方法:** 这个问题可以用位掩码的概念来解决。以下是步骤:
*   将数组 `arr1[]` 的每个字符串转换为其对应的位掩码，如下所示:

```
For string str = "abcd"
the corresponding bitmask conversion is:
characters | value 
    a          0
    b          1
    c          2
    d          3
As per the above characters value, the number is:
value = 2^0 + 2^1 + 2^3 + 2^4
value = 15.
so the string "abcd" represented as 15.
```

*   **注意:** 当位掩码每个字符串时，如果字符的频率大于 1，则只包含相应的字符一次。
*   将每个字符串的频率存储在 `unordered_map` 中。
*   同样，将 `arr2[]` 中的每个字符串转换为相应的位掩码，并执行以下操作:
    *   不计算与 `arr1[]` 对应的所有可能的字，而是使用位操作，使用 `temp = (temp - 1) & val` 找到下一个有效的位掩码。
    *   它产生下一个位掩码模式，通过产生所有可能的组合一次减少一个字符。
*   对于每个有效的排列，检查它是否验证了给定的两个条件，并将相应的频率添加到存储在 `unordered_map` 中的当前字符串中。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

void findNumOfValidWords(vector<string>& w,
                         vector<string>& p)
{
    // To store the frequency of string
    // after bitmasking
    unordered_map<int, int> m;

    // To store result for each string
    // in arr2[]
    vector<int> res;

    // Traverse the arr1[] and bitmask each
    // string in it
    for (string& s : w) {

        int val = 0;

        // Bitmasking for each string s
        for (char c : s) {
            val = val | (1 << (c - 'a'));
        }

        // Update the frequency of string
        // with it's bitmasking value
        m[val]++;
    }

    // Traverse the arr2[]
    for (string& s : p) {
        int val = 0;

        // Bitmasking for each string s
        for (char c : s) {
            val = val | (1 << (c - 'a'));
        }

        int temp = val;
        int first = s[0] - 'a';
        int count = 0;

        while (temp != 0) {

            // Check if temp is present
            // in an unordered_map or not
            if (((temp >> first) & 1) == 1) {
                if (m.find(temp) != m.end()) {
                    count += m[temp];
                }
            }

            // Check for next set bit
            temp = (temp - 1) & val;
        }

        // Push the count for current
        // string in resultant array
        res.push_back(count);
    }

    // Print the count for each string
    for (auto& it : res) {
        cout << it << '\n';
    }
}

// Driver Code
int main()
{
    vector<string> arr1;
    arr1 = { "aaaa", "asas", "able",
             "ability", "actt",
             "actor", "access" };

    vector<string> arr2;
    arr2 = { "aboveyz", "abrodyz",
             "absolute", "absoryz",
             "actresz", "gaswxyz" };

    // Function call
    findNumOfValidWords(arr1, arr2);
    return 0;
}
```

## Java

```java
// Java program for
// the above approach
import java.util.*;
class GFG{

static void findNumOfValidWords(Vector<String> w,
                                Vector<String> p)
{
  // To store the frequency of String
  // after bitmasking
  HashMap<Integer,
          Integer> m = new HashMap<>();

  // To store result for
  // each string in arr2[]
  Vector<Integer> res = new Vector<>();

  // Traverse the arr1[] and
  // bitmask each string in it
  for (String s : w)
  {
    int val = 0;

    // Bitmasking for each String s
    for (char c : s.toCharArray())
    {
      val = val | (1 << (c - 'a'));
    }

    // Update the frequency of String
    // with it's bitmasking value
    if(m.containsKey(val))
      m.put(val, m.get(val) + 1);
    else
      m.put(val, 1);
  }

  // Traverse the arr2[]
  for (String s : p)
  {
    int val = 0;

    // Bitmasking for each String s
    for (char c : s.toCharArray())
    {
      val = val | (1 << (c - 'a'));
    }

    int temp = val;
    int first = s.charAt(0) - 'a';
    int count = 0;

    while (temp != 0)
    {
      // Check if temp is present
      // in an unordered_map or not
      if (((temp >> first) & 1) == 1)
      {
        if (m.containsKey(temp))
        {
          count += m.get(temp);
        }
      }

      // Check for next set bit
      temp = (temp - 1) & val;
    }

    // Push the count for current
    // String in resultant array
    res.add(count);
  }

  // Print the count for each String
  for (int it : res)
  {
    System.out.println(it);
  }
}

// Driver Code
public static void main(String[] args)
{
  Vector<String> arr1 = new Vector<>();
  arr1.add("aaaa"); arr1.add("asas");
  arr1.add("able"); arr1.add("ability");
  arr1.add("actt"); arr1.add("actor");
  arr1.add("access");

  Vector<String> arr2 = new Vector<>();
  arr2.add("aboveyz"); arr2.add("abrodyz");
  arr2.add("absolute"); arr2.add("absoryz");
  arr2.add("actresz"); arr2.add("gaswxyz");

  // Function call
  findNumOfValidWords(arr1, arr2);
}
}

// This code is contributed by Princi Singh
```

## Python 3

```python
# Python3 program for the above approach
from collections import defaultdict

def findNumOfValidWords(w, p):

    # To store the frequency of string
    # after bitmasking
    m = defaultdict(int)

    # To store result for each string
    # in arr2[]
    res = []

    # Traverse the arr1[] and bitmask each
    # string in it
    for s in w:
        val = 0

        # Bitmasking for each string s
        for c in s:
            val = val | (1 << (ord(c) - ord('a')))

        # Update the frequency of string
        # with it's bitmasking value
        m[val] += 1

    # Traverse the arr2[]
    for s in p:
        val = 0

        # Bitmasking for each string s
        for c in s:
            val = val | (1 << (ord(c) - ord('a')))

        temp = val
        first = ord(s[0]) - ord('a')
        count = 0

        while (temp != 0):

            # Check if temp is present
            # in an unordered_map or not
            if (((temp >> first) & 1) == 1):
                if (temp in m):
                    count += m[temp]

            # Check for next set bit
            temp = (temp - 1) & val

        # Push the count for current
        # string in resultant array
        res.append(count)

    # Print the count for each string
    for it in res:
        print(it)

# Driver Code
if __name__ == "__main__":

    arr1 = [ "aaaa", "asas", "able",
             "ability", "actt",
             "actor", "access" ]

    arr2 = [ "aboveyz", "abrodyz",
             "absolute", "absoryz",
             "actresz", "gaswxyz" ]

    # Function call
    findNumOfValidWords(arr1, arr2)

# This code is contributed by chitranayal
```

## C#

```
// C# program for
// the above approach
using System;
using System.Collections.Generic;
class GFG{

static void findNumOfValidWords(List<String> w,
                                List<String> p)
{
  // To store the frequency of String
  // after bitmasking
  Dictionary<int,
             int> m = new Dictionary<int,
                                     int>();

  // To store result for
  // each string in arr2[]
  List<int> res = new List<int>();

  // Traverse the arr1[] and
  // bitmask each string in it
  foreach (String s in w)
  {
    int val = 0;

    // Bitmasking for each String s
    foreach (char c in s.ToCharArray())
    {
      val = val | (1 << (c - 'a'));
    }

    // Update the frequency of String
    // with it's bitmasking value
    if(m.ContainsKey(val))
      m[val] = m[val] + 1;
    else
      m.Add(val, 1);
  }

  // Traverse the arr2[]
  foreach (String s in p)
  {
    int val = 0;

    // Bitmasking for each String s
    foreach (char c in s.ToCharArray())
    {
      val = val | (1 << (c - 'a'));
    }

    int temp = val;
    int first = s[0] - 'a';
    int count = 0;

    while (temp != 0)
    {
      // Check if temp is present
      // in an unordered_map or not
      if (((temp >> first) & 1) == 1)
      {
        if (m.ContainsKey(temp))
        {
          count += m[temp];
        }
      }

      // Check for next set bit
      temp = (temp - 1) & val;
    }

    // Push the count for current
    // String in resultant array
    res.Add(count);
  }

  // Print the count
  // for each String
  foreach (int it in res)
  {
    Console.WriteLine(it);
  }
}

// Driver Code
public static void Main(String[] args)
{
  List<String> arr1 = new List<String>();
  arr1.Add("aaaa"); arr1.Add("asas");
  arr1.Add("able"); arr1.Add("ability");
  arr1.Add("actt"); arr1.Add("actor");
  arr1.Add("access");

  List<String> arr2 = new List<String>();
  arr2.Add("aboveyz"); arr2.Add("abrodyz");
  arr2.Add("absolute"); arr2.Add("absoryz");
  arr2.Add("actresz"); arr2.Add("gaswxyz");

  // Function call
  findNumOfValidWords(arr1, arr2);
}
}

// This code is contributed by shikhasingrajput
```

## java 描述语言

```
<script>

// Javascript program for the above approach

function findNumOfValidWords(w, p)
{
    // To store the frequency of string
    // after bitmasking
    var m = new Map();

    // To store result for each string
    // in arr2[]
    var res = [];

    // Traverse the arr1[] and bitmask each
    // string in it
    w.forEach(s => {
        var val = 0;

        // Bitmasking for each string s
        s.split('').forEach(c => {
            val = val | (1 << (c.charCodeAt(0) - 'a'.charCodeAt(0)));
        });

        // Update the frequency of string
        // with it's bitmasking value
        if(m.has(val))
            m.set(val, m.get(val)+1)
        else
            m.set(val, 1)
    });

    // Traverse the arr2[]
    p.forEach(s => {
        var val = 0;
        s.split('').forEach(c => {
            val = val | (1 << (c.charCodeAt(0) - 'a'.charCodeAt(0)));
        });

        var temp = val;
        var first = s[0].charCodeAt(0) - 'a'.charCodeAt(0);
        var count = 0;

        while (temp != 0) {

            // Check if temp is present
            // in an unordered_map or not
            if (((temp >> first) & 1) == 1) {
                if (m.has(temp)) {
                    count += m.get(temp);
                }
            }

            // Check for next set bit
            temp = (temp - 1) & val;
        }

        // Push the count for current
        // string in resultant array
        res.push(count);
    });

    // Print the count for each string
    res.forEach(it => {

        document.write( it + "<br>");
    });
}

// Driver Code
var arr1 = ["aaaa", "asas", "able",
          "ability", "actt",
          "actor", "access" ];

var arr2 = [ "aboveyz", "abrodyz",
          "absolute", "absoryz",
          "actresz", "gaswxyz" ];
// Function call
findNumOfValidWords(arr1, arr2);

</script>
```

**Output:**

```

```

时间复杂度: `O(N)`
空间复杂度: `O(N)`