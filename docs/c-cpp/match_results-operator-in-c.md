# match_results 运算符=在 C++ 中

> 原文:[https://www.geeksforgeeks.org/match_results-operator-in-c/](https://www.geeksforgeeks.org/match_results-operator-in-c/)

**match_results::运算符=** 用于将一个 smatch 对象中的所有匹配替换为另一个 smatch 对象中的新匹配。
**语法:**

```cpp
smatch_name1 = (smatch_name2)

Note: *smatch_name is an object of match_results class.*
```

**参数:**右侧的 smatch 对象被复制到左侧的对象。
**返回值:**不返回任何东西。
**注意:**第一个元素总是包含整个正则表达式匹配，而其他元素包含特定的[捕获组](https://www.geeksforgeeks.org/smatch-regex-regular-expressions-in-c/)。
以下程序说明了上述功能。
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// match_results operator= in C++
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s("Geeksforgeeks");
    regex re("(Geeks)(.*)");

    smatch match1, match2;

    regex_match(s, match1, re);

    // use of operator =--> assigns all
    // the contents of match1 to match2
    match2 = match1;

    cout << "Matches are:" << endl;
    for (smatch::iterator it = match2.begin();
         it != match2.end(); it++) {
        cout << *it << endl;
    }
}
```

**Output:** 

```cpp
Matches are:
Geeksforgeeks
Geeks
forgeeks
```

**节目 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// match_results operator= in C++
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s("Geeksforgeeks");
    regex re1("(Geeks)(.*)");
    regex re2("(Ge)(eks)(.*)");

    smatch match1, match2;

    regex_match(s, match1, re1);
    regex_match(s, match2, re2);

    smatch max_match;

    // use of operator =--> assigns all
    // the contents of match1 to match2
    if (match1.size() > match2.size()) {
        max_match = match1;
    }
    else {
        max_match = match2;
    }

    cout << "Smatch with maximum matches:" << endl;
    for (smatch::iterator it = max_match.begin();
         it != max_match.end(); it++) {
        cout << *it << endl;
    }
}
```

**Output:** 

```cpp
Smatch with maximum matches:
Geeksforgeeks
Ge
eks
forgeeks
```