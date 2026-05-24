# C++ STL 中 unordered_map::max_size

> 原文: [https://www.geeksforgeeks.org/unordered_map-max_size-in-c-stl/](https://www.geeksforgeeks.org/unordered_map-max_size-in-c-stl/)

`unordered_map::max_size` 是 C++ STL 中的内置函数。它返回无序映射可以容纳的最大元素数。任何容器中元素的最大数量取决于系统和库的实现。

## 语法

```cpp
size_type unordered_map.max_size()
```

## 参数

不接受任何参数。

## 返回类型

无符号整数。一个容器最多可以容纳的元素个数。

## 例 1

```cpp
// C++ program to illustrate the
// unordered_map::max_size function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration of unordered_map
    unordered_map<int, int> sample;

    cout << " Current size is :  " << sample.size() << endl;
    cout << " max size is : " << sample.max_size() << endl;

    // insert elements
    sample.insert({ 1, 10 });
    sample.insert({ 2, 10 });
    sample.insert({ 3, 10 });
    sample.insert({ 4, 10 });

    cout << " Current size is :  " << sample.size() << endl;
    cout << " max size is : " << sample.max_size() << endl;

    return 0;
}
```

**Output:**

```cpp
Current size is :  0
 max size is : 1152921504606846975
 Current size is :  4
 max size is : 1152921504606846975
```

## 例 2

```cpp
// C++ program to illustrate the
// unordered_map::max_size function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration of unordered_map
    unordered_map<char, int> sample;

    cout << " Current size is :  " << sample.size() << endl;
    cout << " max size is : " << sample.max_size() << endl;

    // insert elements
    sample.insert({ 'a', 10 });
    sample.insert({ 'b', 10 });
    sample.insert({ 'c', 10 });

    cout << " Current size is :  " << sample.size() << endl;
    cout << " max size is : " << sample.max_size() << endl;

    return 0;
}
```

**Output:**

```cpp
Current size is :  0
 max size is : 1152921504606846975
 Current size is :  3
 max size is : 1152921504606846975
```

## 复杂度

其复杂度不变。