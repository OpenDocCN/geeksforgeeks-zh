# c++ STL 中的 deque insert()函数

> 原文: [https://www.geeksforgeeks.org/deque-insert-function-in-c-stl/](https://www.geeksforgeeks.org/deque-insert-function-in-c-stl/)

`deque::insert()` 函数是 C++ 中的内置函数，用于在 deque 中插入元素。
`insert()` 函数有三种使用方式:

*   通过在 `position` 插入新元素 `val` 来扩展 deque。
*   通过将 `n` 个新元素 `val` 插入到 deque 中来扩展 deque。
*   通过在范围 `[first, last)` 中插入新元素来扩展 deque。

## 语法:

```cpp
deque_name.insert (iterator position, const value_type& val)
                or
deque_name.insert (iterator position, size_type n, const value_type& val)
                or
deque_name.insert (iterator position, InputIterator first, InputIterator last)
```

## 参数:

该函数接受如下指定的四个参数:

*   `position` – 指定要插入元素的位置。
*   `val` – 指定要分配给新插入元素的值。
*   `n` – 指定要插入的元素数量。每个元素都被初始化为 `val` 的一个副本。
*   `first, last` – 指定迭代器，定义要插入的元素范围。范围包括 `first` 和 `last` 之间的所有元素，包括 `first` 指向的元素，但不包括 `last` 指向的元素。

## 返回值:

函数返回一个迭代器，指向新插入的第一个元素。

## 以下程序说明了上述功能:

### 程序 1:

```cpp
// CPP program to illustrate the
// deque::insert() function
// insert elements by iterator
#include <bits/stdc++.h>
using namespace std;

int main()
{
    deque<int> dq = { 1, 2, 3, 4, 5 };

    deque<int>::iterator it = dq.begin();
    ++ it;

    it = dq.insert(it, 10); // 1 10 2 3 4 5

    std::cout << "Deque contains:";
    for (it = dq.begin(); it != dq.end(); ++ it)
        cout << ' ' << *it;
    cout << '\n';

    return 0;
}
```

**Output:**

```cpp
Deque contains: 1 10 2 3 4 5
```

### 程序 2:

```cpp
// CPP program to illustrate the
// deque::insert() function
// program for second syntax
#include <bits/stdc++.h>
using namespace std;

int main()
{
    deque<int> dq = { 1, 2, 3, 4, 5 };

    deque<int>::iterator it = dq.begin();

    // 0 0 1 2 3 4 5
    dq.insert(it, 2, 0);

    std::cout << "Deque contains:";

    for (it = dq.begin(); it != dq.end(); ++ it)
        cout << ' ' << *it;
    cout << '\n';

    return 0;
}
```

**Output:**

```cpp
Deque contains: 0 0 1 2 3 4 5
```

### 程序 3:

```cpp
// CPP program to illustrate the
// deque::insert() function
// program for third syntax
#include <bits/stdc++.h>
using namespace std;

int main()
{
    deque<int> dq = { 1, 2, 3, 4, 5 };

    deque<int>::iterator it = dq.begin();
    ++ it;

    vector<int> v(2, 10);

    // 1 10 10 2 3 4 5
    dq.insert(it, v.begin(), v.end());

    std::cout << "Deque contains:";
    for (it = dq.begin(); it != dq.end(); ++ it)
        cout << ' ' << *it;
    cout << '\n';

    return 0;
}
```

**Output:**

```cpp
Deque contains: 1 10 10 2 3 4 5
```