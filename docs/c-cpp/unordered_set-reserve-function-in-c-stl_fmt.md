# C++ STL 中的 `unordered_set::reserve()` 函数

> 原文：[https://www.geeksforgeeks.org/unordered_set-reserve-function-in-c-stl/](https://www.geeksforgeeks.org/unordered_set-reserve-function-in-c-stl/)

`unordered_set::reserve()` 方法是 C++ STL 中的一个内置函数，用于请求 `unordered_set` 的容量变化。它将容器中的桶数设置为至少包含 `n` 个元素。如果 `n` 大于当前的 `bucket_count` 乘以 `max_load_factor`，容器的桶数将增加并强制重新散列。如果 `n` 小于 `bucket_count`，则该函数不起作用。

## 语法
```cpp
unordered_set_name.reserve(size_type n)
```

## 参数
该函数接受一个强制参数 `n`，该参数将容器中的桶数 (`bucket_count`) 设置为最适合包含至少 `n` 个元素的值。

## 返回值
这个函数不返回任何值。

下面的程序说明了 `unordered_set::reserve()` 函数：

## 程序 1
```cpp
// C++ program to illustrate
// the unordered_set.reserve()
#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{
    // Declaration of unordered_set
    unordered_set<string> us;

    us.reserve(3);

    us.insert("geeks");
    us.insert("for");
    us.insert("geeks");
    us.insert("users");
    us.insert("geeksforgeeks");

    for (auto it = us.begin(); it != us.end(); it++) {
        cout << *it << " ";
    }

    return 0;
}
```
**输出：**
```
geeksforgeeks users geeks for
```

## 程序 2
```cpp
// C++ program to illustrate
// the unordered_set.reserve()
#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{
    // Declaration of unordered_set
    unordered_set<string> us;

    us.reserve(0);

    us.insert("geeks");
    us.insert("for");
    us.insert("geeks");

    for (auto it = us.begin(); it != us.end(); it++) {
        cout << *it << " ";
    }

    return 0;
}
```
**输出：**
```
for geeks
```