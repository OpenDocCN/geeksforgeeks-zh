# match_results size() in C++ STL

> 原文: [https://www.geeksforgeeks.org/match_results-size-in-c-stl/](https://www.geeksforgeeks.org/match_results-size-in-c-stl/)

`match_results::size()` 是 C++ 中的一个内置函数，它返回 `match_result` 对象中的匹配数和子匹配数。

## 语法

```cpp
smatch_name.size()
```

注意：`smatch_name` 是 `match_results` 类的一个对象。

## 参数

该函数不接受参数。

## 返回值

返回 `match_result` 对象中的匹配数。

## 注意

第一个元素总是包含整个正则表达式匹配，而其他元素包含特定的[捕获组](https://www.geeksforgeeks.org/smatch-regex-regular-expressions-in-c/)。下面的程序说明了上述功能。

## 示例 1

```cpp
// CPP program to illustrate
// match_results size() in C++
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s("Geeksforgeeks");
    regex re("(Geeks)(.*)");

    smatch match;

    // Function call to find match
    regex_match(s, match, re);

    cout << "match size is " << match.size() << endl;

    return 0;
}
```

**输出:**

```cpp
match size is 3
```

## 示例 2

```cpp
// CPP program to illustrate
// match_results size() in C++
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s("Geeksforgeeks");
    regex re("(Geeks)(.*)");

    smatch match;

    // Function call to find matches
    regex_match(s, match, re);

    cout << "match size is " << match.size() << endl;

    for (int i = 0; i < match.size(); i++) {
        cout << "match " << i << " has a length of "
             << match.length(i) << endl;
    }
    return 0;
}
```

**输出:**

```cpp
match size is 3
match 0 has a length of 13
match 1 has a length of 5
match 2 has a length of 8
```