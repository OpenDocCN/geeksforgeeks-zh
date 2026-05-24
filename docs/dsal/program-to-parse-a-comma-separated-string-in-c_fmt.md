# 用 C++ 解析逗号分隔字符串的程序

> 原文: [https://www.geeksforgeeks.org/program-to-parse-a-comma-separated-string-in-c/](https://www.geeksforgeeks.org/program-to-parse-a-comma-separated-string-in-c/)

给定一个逗号分隔的字符串，任务是解析这个字符串并在 C++ 中分隔单词。

`例:`

```
Input: "1,2,3,4,5"
Output:
1
2
3
4
5

Input: "Geeks,for,Geeks"
Output:
Geeks
for
Geeks
```

`进场:`

*   获取流中的字符串 – [`stringstream`](https://www.geeksforgeeks.org/stringstream-c-applications/)
*   创建一个字符串向量来存储解析的单词
*   直到 `stringstream` 中有一个字符串，用 `good()` 方法检查，
    *   使用 [`getline()`](https://www.geeksforgeeks.org/getline-string-c/) 方法获取字符串从起点到第一个出现的子字符串
    *   这将给出子串中的单词
    *   现在把这个单词存储在向量中
    *   这个单词现在从流中移除并存储在向量中

以下是上述方法的实现:

## C++ 实现

```cpp
// C++ program to parse a comma-separated string

#include <bits/stdc++.h>
using namespace std;

int main()
{
    string str = "1,2,3,4,5,6";
    vector<string> v;

    stringstream ss(str);

    while (ss.good()) {
        string substr;
        getline(ss, substr, ',');
        v.push_back(substr);
    }

    for (size_t i = 0; i < v.size(); i++)
        cout << v[i] << endl;
}
```

`Output:`

```
1
2
3
4
5
6
```