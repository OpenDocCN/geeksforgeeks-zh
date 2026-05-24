# 在 C++ 中使用无序映射的字符串中每个字符的频率

> 原文:[https://www . geeksforgeeks . org/字符串中每个字符使用无序映射的频率-in-c/](https://www.geeksforgeeks.org/frequency-of-each-character-in-a-string-using-unordered_map-in-c/)

给定一个字符串 **str** ，任务是使用 [C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 中的[无序 _ 映射](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/)找到一个字符串的每个字符的频率。

**示例:**

> **输入:**str = " geeks forgeeks "
> T3】输出:T5】r 1
> e 4
> s 2
> g 2
> k 2
> f 1
> o 1
> 
> **输入:** str = "programming"
> **输出:**
> n 1
> I 1
> p 1
> o 1
> r 2
> a 1
> g 2
> m 2

**进场:**

1.  遍历给定字符串**字符串**的每个字符。
2.  检查当前字符是否出现在[无序 _ 地图](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/)中。
3.  如果存在，则更新当前字符的频率，否则插入频率为 1 的字符，如下所示:

```cpp
if(M.find(s[i])==M.end()) {
    M.insert(make_pair{s[i], 1});
}
else {
    M[s[i]]++ ;
}

```

4.遍历[无序 _ 映射](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/)并打印作为映射值存储的每个字符的频率。

下面是上述方法的实现:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

void printFrequency(string str)
{
    // Define an unordered_map
    unordered_map<char, int> M;

    // Traverse string str check if
    // current character is present
    // or not
    for (int i = 0; str[i]; i++)
    {
        // If the current characters
        // is not found then insert
        // current characters with
        // frequency 1
        if (M.find(str[i]) == M.end())
        {
            M.insert(make_pair(str[i], 1));
        }

        // Else update the frequency
        else
        {
            M[str[i]]++ ;
        }
    }

    // Traverse the map to print the
    // frequency
    for (auto& it : M) {
        cout << it.first << ' ' << it.second << '\n';
    }
}

// Driver Code
int main()
{
    string str = "geeksforgeeks";

    // Function call
    printFrequency(str);
    return 0;
}
```

**Output**

```cpp
r 1
e 4
s 2
g 2
k 2
f 1
o 1

```