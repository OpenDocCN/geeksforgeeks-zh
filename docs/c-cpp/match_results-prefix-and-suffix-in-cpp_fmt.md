# C++ 中 `match_results` 的 `prefix()` 和 `suffix()`

> 原文: [https://www.geeksforgeeks.org/match_results-prefix-and-suffix-in-cpp/](https://www.geeksforgeeks.org/match_results-prefix-and-suffix-in-cpp/)

*   `match_results::prefix()` 是 C++ 中的一个内置函数，用于获取输入目标字符串中匹配字符串之前的字符串。

    **语法:**
    ```cpp
    smatch_name.prefix()
    ```
    Note: `smatch_name` 是 `match_results` 类的一个对象。

*   **参数:** 此功能不接受参数。
*   **返回值:** 该函数返回目标字符串中匹配序列之前的序列。
*   **注意:** 第一个元素总是包含整个正则表达式匹配，而其他元素包含特定的[捕获组](https://www.geeksforgeeks.org/smatch-regex-regular-expressions-in-c/)。

以下程序说明上述功能:

## 示例程序

```cpp
// CPP program to illustrate
// match_results prefix() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s("Geeksforgeeks is a computer science portal");
    regex re("computer");
    smatch match;
    regex_search(s, match, re);
    cout << "Prefix is: [";
    if (!match.empty()) {
        cout << match.prefix() << "]" << endl;
    }
    return 0;
}
```

**Output:**
```cpp
Prefix is: [Geeksforgeeks is a ]
```

*   `match_results::suffix()` 是 C++ 中的一个内置函数，用于获取输入目标字符串中匹配字符串之后的字符串。

    **语法:**
    ```cpp
    smatch_name.suffix()
    ```
    Note: `smatch_name` 是 `match_results` 类的一个对象。

*   **参数:** 此功能不接受参数。
*   **返回值:** 该函数返回目标字符串中匹配序列之后的序列。
*   **注意:** 第一个元素总是包含整个正则表达式匹配，而其他元素包含特定的[捕获组](https://www.geeksforgeeks.org/smatch-regex-regular-expressions-in-c/)。

以下程序说明上述功能:

## 示例程序

```cpp
// CPP program to illustrate
// match_results suffix() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s("Geeksforgeeks is a computer science portal");
    regex re("computer");
    smatch match;
    regex_search(s, match, re);
    cout << "Suffix is: [";
    if (!match.empty()) {
        cout << match.suffix() << "]" << endl;
    }
    return 0;
}
```

**Output:**
```cpp
Suffix is: [ science portal]
```