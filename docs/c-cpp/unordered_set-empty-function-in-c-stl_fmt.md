# `unordered_set::empty()` 函数

> 原文: [https://www.geeksforgeeks.org/unordered_set-empty-function-in-c-stl/](https://www.geeksforgeeks.org/unordered_set-empty-function-in-c-stl/)

`unordered_set::empty()` 是 C++ STL 中的内置函数，用于检查 `unordered_set` 容器是否为空。如果无序集容器为空，则返回真，否则返回假。

## 语法

```cpp
map_name.empty()
```

## 参数

该功能不接受任何参数。

## 返回值

如果无序集容器为空，则返回布尔值 `true`，否则返回 `false`。

以下程序说明了上述功能：

## 程序 1

```cpp
// C++ program to illustrate the
// unordered_set::empty function
#include <iostream>
#include <unordered_set>
using namespace std;

int main()
{
    // declaration
    unordered_set<int> sample;

    // Check whether the unordered_set is empty
    if (sample.empty() == true)
        cout << "true" << endl;
    else
        cout << "false" << endl;

    // Insert a value
    sample.insert(5);

    // Now check whether it is empty
    if (sample.empty() == true)
        cout << "true" << endl;
    else
        cout << "false" << endl;

    return 0;
}
```

**输出:**

```cpp
true
false
```

## 程序 2

```cpp
// C++ program to illustrate the
// unordered_set::empty function
#include <iostream>
#include <unordered_set>
using namespace std;

int main()
{
    // declaration
    unordered_set<int> uset;

    // Insert a value
    uset.insert({ 5, 6, 7, 8 });
    // Check whether the unordered_set is empty
    if (uset.empty() == true)
        cout << "true" << endl;
    else
        cout << "false" << endl;

    return 0;
}
```

**输出:**

```cpp
false
```