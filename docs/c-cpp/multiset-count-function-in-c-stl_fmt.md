# C++ STL 中的 multiset::count() 函数

> 原文: [https://www.geeksforgeeks.org/multiset-count-function-in-c-stl/](https://www.geeksforgeeks.org/multiset-count-function-in-c-stl/)

`multiset::count()` 函数是 C++ STL 中的内置函数，它在 multiset 容器中搜索特定元素，并返回该元素的出现次数。

## 语法

```cpp
multiset_name.count(val)
```

## 参数

该函数接受单个参数 `val`，该参数指定要在 multiset 容器中搜索的元素。

## 返回值

该函数返回 multiset 容器中等于 `val` 的元素计数。

下面的程序说明了 `multiset::count()` 函数：

## 程序 1

```cpp
// C++ program to demonstrate the
// multiset::count() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    int arr[] = { 15, 10, 15, 11, 10, 18, 18, 20, 20 };

    // initializes the set from an array
    multiset<int> s(arr, arr + 9);

    cout << "15 occurs " << s.count(15)
         << " times in container";

    return 0;
}
```

### 输出

```cpp
15 occurs 2 times in container
```

## 程序 2

```cpp
// C++ program to demonstrate the
// multiset::count() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    int arr[] = { 15, 10, 15, 11, 10, 18, 18, 18, 18 };

    // initializes the set from an array
    multiset<int> s(arr, arr + 9);

    cout << "18 occurs " << s.count(18)
         << " times in container";

    return 0;
}
```

### 输出

```cpp
18 occurs 4 times in container
```

`multiset::count()` 函数的时间复杂度为 `O(K + log(N))`，其中 `K` 是传递的值的整数总数。