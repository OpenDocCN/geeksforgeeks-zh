# c++ STL 中 match_results begin()和 end()函数

> 原文:[https://www . geesforgeks . org/match _ results-begin-and-end-function-in-c-STL/](https://www.geeksforgeeks.org/match_results-begin-and-end-function-in-c-stl/)

*   **match_results::cbegin()** 是 C++ STL 中的一个内置函数，它返回一个指向 match_results 对象中第一个匹配的迭代器。
    **语法:**

```cpp
smatch_name.begin()
```

*   **参数:**此功能不接受任何参数。
    **返回值:**这个函数返回一个迭代器，指向 match_results 对象中的第一个匹配项。match_results 对象中包含的匹配总是恒定的。
    **注意:**第一个元素总是包含整个正则表达式匹配，而其他元素包含特定的[捕获组](https://www.geeksforgeeks.org/smatch-regex-regular-expressions-in-c/)。
    以下程序说明上述功能:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// match_results begin() function
#include <bits/stdc++.h>
using namespace std;
int main()
{
    string sp("geeksforgeeks");
    regex re("(geeks)(.*)");

    smatch match;

    // we can use member function on match
    // to extract the matched pattern.
    std::regex_match(sp, match, re);

    // The size() member function indicates the
    // number of capturing groups plus one for the overall match
    // match size = Number of capturing group + 1
    // (.*) which "forgeeks" ).
    cout << "Match size = " << match.size() << endl;

    cout << "matches:" << endl;
    for (smatch::iterator it = match.begin(); it != match.end(); ++ it)
        cout << *it << endl;
    return 0;
}
```

**Output:** 

```cpp
Match size = 3
matches:
geeksforgeeks
geeks
forgeeks
```

*   **match_results::end()** 是 C++ STL 中的一个内置函数，它返回一个迭代器，指向 match_results 对象中的结束匹配。
    **语法:**

```cpp
smatch_name.end()
```

*   **参数:**此功能不接受任何参数。
    **返回值:**这个函数返回一个迭代器，指向 match_results 对象中的结束匹配。match_results 对象中包含的匹配总是恒定的。
    **注意:**第一个元素总是包含整个正则表达式匹配，而其他元素包含特定的[捕获组](https://www.geeksforgeeks.org/smatch-regex-regular-expressions-in-c/)。
    以下程序说明上述功能

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// match_results end() function
#include <bits/stdc++.h>
using namespace std;
int main()
{
    string sp("matchresult");
    regex re("(match)(.*)");

    smatch match;

    // we can use member function on match
    // to extract the matched pattern.
    std::regex_match(sp, match, re);

    // The size() member function indicates the
    // number of capturing groups plus one for the overall match
    // match size = Number of capturing group + 1
    // (.*) which "results" ).
    cout << "Match size = " << match.size() << endl;

    cout << "matches:" << endl;
    for (smatch::iterator it = match.begin(); it != match.end(); ++ it)
        cout << *it << endl;
    return 0;
}
```

**Output:** 

```cpp
Match size = 3
matches:
matchresult
match
result
```