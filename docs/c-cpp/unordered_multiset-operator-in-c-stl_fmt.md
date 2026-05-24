# C++ STL 中的 `unordered_multiset::operator=`

> 原文: [https://www.geeksforgeeks.org/unordered_multiset-operator-in-c-stl/](https://www.geeksforgeeks.org/unordered_multiset-operator-in-c-stl/)

`=` 是 `C++ STL` 中的一个运算符，它将一个 `unordered_multiset` 复制（或移动）到另一个 `unordered_multiset`，而 `unordered_multiset::operator=` 是对应的运算符函数。该功能有三个版本：

## 版本一：复制赋值

第一个版本接受一个 `unordered_multiset` 的引用作为参数，并将其复制到另一个 `unordered_multiset`。

**语法：**

```cpp
ums1.operator=(unordered_multiset &ums2)
```

**参数：** 第一个版本以一个 `unordered_multiset` 的引用作为参数。

## 版本二：移动赋值

第二个版本执行移动赋值，即将一个 `unordered_multiset` 的内容移动到另一个 `unordered_multiset`。

**语法：**

```cpp
ums1.operator=(unordered_multiset &&ums2)
```

**参数：** 第二个版本以 `unordered_multiset` 的右值引用作为参数。

## 版本三：初始化列表赋值

第三个版本将初始化列表的内容赋值给一个 `unordered_multiset`。

**语法：**

```cpp
ums1.operator=(initializer_list)
```

**参数：** 第三个版本以一个初始化列表作为参数。

**返回值：** 所有版本都返回 `*this` 的值。

## 示例

以下程序说明了 `unordered_multiset::operator=` 的用法。

```cpp
// C++ code to illustrate the method
// unordered_multiset::operator=()

#include <iostream>
#include <unordered_set>
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
    unordered_multiset<int> sample1, sample2, sample3;

    // List initialization
    sample1 = { 1, 2, 2, 3, 3, 4, 4, 4, 3, 4 };
    sample2 = { 1, 2, 3, 1, 4 };

    // Merge both unordered_multisets and
    // move the result to sample1
    sample3 = merge(sample1, sample2);

    // copy assignment
    sample1 = sample3;

    // Print the unordered_set list
    for (auto it = sample1.begin(); it != sample1.end(); ++ it)
        cout << *it << " ";
    cout << endl;

    for (auto it = sample2.begin(); it != sample2.end(); ++ it)
        cout << *it << " ";
    cout << endl;

    for (auto it = sample3.begin(); it != sample3.end(); ++ it)
        cout << *it << " ";
    cout << endl;
}
```

**输出：**

```cpp
1 1 1 2 2 2 3 3 3 3 4 4 4 4 4 
4 3 2 1 1 
1 1 1 2 2 2 3 3 3 3 4 4 4 4 4
```