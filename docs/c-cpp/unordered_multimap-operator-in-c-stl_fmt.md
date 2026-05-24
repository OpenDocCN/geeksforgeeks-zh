# 无序多映射 `operator=` 在 C++ STL 中

> 原文: <https://www.geeksforgeeks.org/unordered_multimap-operator-in-c-stl/>

`=` 是 C++ STL 中的一个运算符，它将一个无序多映射复制（或移动）到另一个无序多映射，而 `unordered_multimap::operator=` 是对应的运算符函数。这个函数有三个版本。

1.  第一个版本以无序多映射的引用作为参数，并将其复制到无序多映射。
2.  第二个版本执行移动分配，即它将无序多映射的内容移动到另一个无序多映射。
3.  第三个版本将初始化列表的内容分配给无序多映射。

## 语法

```cpp
umm.operator=( unordered_multimap& umm )
umm.operator=( unordered_multimap&& umm )
umm.operator=( initializer_list )
```

## 参数

1.  第一个版本以无序多映射的引用作为参数。
2.  第二个版本将无序多映射的右值引用作为参数。
3.  第三个版本以初始化列表作为参数。

## 返回值

都返回这个指针的值（`*this`）。

下面的程序说明了 C++ 中的 `unordered_multimap::operator=` 的用法。

## 示例

```cpp
// C++ code to illustrate the method
// unordered_multimap::operator=()
#include <bits/stdc++.h>

using namespace std;

// merge function
template <class T>
T merge(T a, T b)
{
    T t(a);
    t.insert(b.begin(), b.end());
    return t;
}

int main()
{
    unordered_multimap<int, int> sample1, sample2, sample3;

    // List initialization
    sample1 = { { 1, 2 }, { 3, 4 }, { 5, 6 } };
    sample2 = { { 7, 8 }, { 9, 10 }, { 11, 12 } };

    // Merge both lists
    sample3 = merge(sample1, sample2);

    // copy assignment
    sample1 = sample3;

    // Print the unordered_multimap list
    for (auto& it : sample1)
        cout << it.first << " : " << it.second << endl;
    cout << endl;
    for (auto& it : sample2)
        cout << it.first << " : " << it.second << endl;
    cout << endl;
    for (auto& it : sample3)
        cout << it.first << " : " << it.second << endl;
    return 0;
}
```

## 输出

```cpp
7 : 8
9 : 10
11 : 12
1 : 2
3 : 4
5 : 6

11 : 12
9 : 10
7 : 8

7 : 8
9 : 10
11 : 12
1 : 2
3 : 4
5 : 6
```