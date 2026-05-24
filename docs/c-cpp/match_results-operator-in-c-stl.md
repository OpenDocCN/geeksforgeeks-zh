# c++ STL 中的 match_results 运算符[]

> 原文:[https://www . geesforgeks . org/match _ results-operator-in-c-STL/](https://www.geeksforgeeks.org/match_results-operator-in-c-stl/)

**match_results::operator[]**是 C++ 中的一个内置函数，用于获取 match _ result 对象中的第*个*匹配。它在运算符内部给定的位置给出匹配的引用。
**语法:**

```cpp
smatch_name[N]

Note: *smatch_name is an object of match_results class.*
```

**参数:**它接受指定匹配号的单个参数 N。它低于 match_results::size。匹配数字 0 表示整个匹配表达式。随后的匹配号标识子表达式(如果有)。传递的整数是无符号整数类型。
**返回值:**返回第 N 场比赛对比赛的直接引用。
**注意:**第一个元素总是包含整个正则表达式匹配，而其他元素包含特定的[捕获组](https://www.geeksforgeeks.org/smatch-regex-regular-expressions-in-c/)。
以下程序说明了上述功能。
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// match_results operator[] in C++
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s("Geeksforgeeks");
    regex re("(Geeks)(.*)");

    smatch match;

    regex_match(s, match, re);

    // use of operator[]--> returns the
    // reference to the match at i-th position
    cout << "Matches are:" << endl;
    for (int i = 0; i < match.size(); i++) {
        cout << "match " << i << " is " << match[i] << endl;
    }
}
```

**Output:** 

```cpp
Matches are:
match 0 is Geeksforgeeks
match 1 is Geeks
match 2 is forgeeks
```

**节目 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// match_results operator[] in C++
// Find maximum length
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s("Geeksforgeeks");
    regex re("(Ge)(eks)(.*)");

    smatch match;

    regex_match(s, match, re);

    int max_length = 0;
    string str;

    // Since the first match is the whole string we do not consider it.
    for (int i = 1; i < match.size(); i++) {
        if (match.length(i) > max_length) {
            str = match[i];
            max_length = match.length(i);
        }
    }

    cout << "max-length sub match is " << str
         << " with a length of " << max_length << endl;
    return 0;
}
```

**Output:** 

```cpp
max-length sub match is forgeeks with a length of 8
```