# match_results cbegin()与cend()在C++ STL中的使用

> 原文：[https://www.geeksforgeeks.org/match_results-cbegin-add-cend-in-c-stl/](https://www.geeksforgeeks.org/match_results-cbegin-add-cend-in-c-stl/)

## match_results::cbegin()

`match_results::cbegin()`是C++ STL中的一个内置函数，它返回一个指向`match_results`对象中第一个匹配项的常量迭代器。这个迭代器不能修改向量的内容。

**语法：**

```cpp
smatch_name.cbegin()
```

**参数：** 此函数不接受任何参数。
**返回值：** 这个函数返回一个常量迭代器，指向`match_results`对象中的第一个匹配项。`match_results`对象中包含的匹配总是恒定的。
**注意：** 第一个元素总是包含整个正则表达式匹配，而其他元素包含特定的[捕获组](https://www.geeksforgeeks.org/smatch-regex-regular-expressions-in-c/)。

以下程序说明上述功能。

### 示例程序

```cpp
// C++ program to illustrate the
// match_result function
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
    for (smatch::iterator it = match.cbegin(); it != match.cend(); ++ it)
        cout << *it << endl;
    return 0;
}
```

**输出：**

```cpp
Match size=3
matches:
geeksforgeeks
geeks
forgeeks
```

## match_results::cend()

`smatch::cend()`是C++ STL中的一个内置函数，它返回一个常量迭代器，指向`match_results`对象中的结束匹配。这个迭代器不能修改向量的内容。

**语法：**

```cpp
smatch_name.cend()
```

**参数：** 此函数不接受任何参数。
**返回值：** 这个函数返回一个常量迭代器，指向`match_results`对象中的结束匹配。`match_results`对象中包含的匹配总是恒定的。
**注意：** 第一个元素总是包含整个正则表达式匹配，而其他元素包含特定的[捕获组](https://www.geeksforgeeks.org/smatch-regex-regular-expressions-in-c/)。

以下程序说明上述功能。

### 示例程序

```cpp
// C++ program to illustrate the
// match_results cend() function
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
    for (smatch::iterator it = match.cbegin(); it != match.cend(); ++ it)
        cout << *it << endl;
    return 0;
}
```

**输出：**

```cpp
Match size=3
matches:
matchresults
match
results
```