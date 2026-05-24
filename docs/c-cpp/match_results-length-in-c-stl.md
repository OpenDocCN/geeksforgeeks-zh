# c++ STL 中的 match_results length()

> 原文:[https://www . geesforgeks . org/match _ results-length-in-c-STL/](https://www.geeksforgeeks.org/match_results-length-in-c-stl/)

**match_results::length()** 是 C++ 中的一个内置函数，用于返回 match_results 对象中特定匹配的长度。
**语法:**

```cpp
smatch_name.length(n)

Note: *smatch_name is an object of match_results class.*
```

**参数:**它接受指定匹配号的单个参数 n。它低于 match_results::size。匹配数字 0 表示整个匹配表达式。随后的匹配号标识子表达式(如果有)。传递的整数是无符号整数类型。
**返回值:**返回 match_results 对象中*第 n 次*匹配的长度。
**注意:**第一个元素总是包含整个正则表达式匹配，而其他元素包含特定的[捕获组](https://www.geeksforgeeks.org/smatch-regex-regular-expressions-in-c/)。
下面的程序说明了上述功能。
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// match_results length() in C++
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s("Geeksforgeeks");
    regex re("(Geeks)(.*)");

    smatch match;

    regex_match(s, match, re);

    for (int i = 0; i < match.size(); i++) {
        cout << "match " << i << " has a length of "
             << match.length(i) << endl;
    }
    return 0;
}
```

**Output:** 

```cpp
match 0 has a length of 13
match 1 has a length of 5
match 2 has a length of 8
```

**节目 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// match_results length() in C++
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

    // Since the first match is the
    // whole string we do not consider it.
    for (int i = 1; i < match.size(); i++) {
        if (match.length(i) > max_length) {
            str = match[i];
            max_length = match.length(i);
        }
    }

    cout << "max-length sub match is " << str
         << " with a length of " << max_length;
    return 0;
}
```

**Output:** 

```cpp
max-length sub match is forgeeks with a length of 8
```