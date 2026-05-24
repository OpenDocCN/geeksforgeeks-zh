# 在 C++ STL 中 match_results 为空()

> 原文:[https://www.geeksforgeeks.org/match_results-empty-in-c-stl/](https://www.geeksforgeeks.org/match_results-empty-in-c-stl/)

**match_results::empty()** 是 C++ 中的一个内置函数，如果 smatch 对象不包含匹配项，则返回 **True** 。
**语法:**

```cpp
smatch_name.empty()

Note: *smatch_name is an object of match_results class.*
```

**参数:**此功能不接受参数。
**返回值:**当对象是默认构造的时，此函数返回真，否则如果正则表达式匹配或正则表达式搜索至少找到一个匹配，则返回假。
**错误和异常:**

*   它没有异常抛出保证。
*   传递参数时引发异常。

**注意:**第一个元素总是包含整个正则表达式匹配，而其他元素包含特定的[捕获组](https://www.geeksforgeeks.org/smatch-regex-regular-expressions-in-c/)。
下面的程序说明了上述方法。
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// match_results empty() in C++
#include<bits/stdc++.h>
using namespace std;

int main()
{
    string s("harsha");
    regex re1("Geeks.*");
    regex re2("geeks.*");

    smatch match1, match2;

    regex_match(s, match1, re1);
    regex_match(s, match2, re2);

    // if match1 is empty it returns
    // true or else false
    if (match1.empty()) {
        cout << "Regex-1 did not match" << endl;
    }
    else {
        cout << "Regex-1 matched" << endl;
    }

    // if match2 is empty it returns
    // true or else false
    if (match2.empty()) {
        cout << "Regex-2 did not match" << endl;
    }
    else {
        cout << "Regex-2 matched" << endl;
    }

    return 0;
}
```

**Output:** 

```cpp
Regex-1 did not match
Regex-2 did not match
```

**节目 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// match_results empty() in C++
#include<bits/stdc++.h>
using namespace std;

int main()
{
    string s("geeksforgeeks");
    regex re1("Geeks.*");
    regex re2("geeks.*");

    smatch match1, match2;

    regex_match(s, match1, re1);
    regex_match(s, match2, re2);

    // if match1 is empty it returns
    // true or else false
    if (match1.empty()) {
        cout << "Regex-1 did not match" << endl;
    }
    else {
        cout << "Regex-1 matched" << endl;
    }

    // if match2 is empty it returns
    // true or else false
    if (match2.empty()) {
        cout << "Regex-2 did not match" << endl;
    }
    else {
        cout << "Regex-2 matched" << endl;
    }

    return 0;
}
```

**Output:** 

```cpp
Regex-1 did not match
Regex-2 matched
```