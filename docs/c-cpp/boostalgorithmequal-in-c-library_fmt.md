# boost::algorithm::equal() 在 C++ 库中

> 原文：[https://www.geeksforgeeks.org/boostalgorithmequal-in-c-library/](https://www.geeksforgeeks.org/boostalgorithmequal-in-c-library/)

[C++ boost 库](https://www.geeksforgeeks.org/advanced-c-boost-library/) 中的 `equal()` 函数位于头文件 `boost/algorithm/cxx11/equal.hpp` 下，用于测试两个序列是否包含相等的值。它返回一个布尔值，确定两个序列是否相同。

## 语法

```cpp
bool equal ( InputIterator1 first1, InputIterator1 second1,
                  InputIterator2 first2, InputIterator2 second2 )
or 
bool equal ( InputIterator1 first1, InputIterator1 second1,
             InputIterator2 first2, InputIterator2 second2, 
             BinaryPredicate pred )
```

## 参数

该函数接受如下参数：

*   `first1`：指定第一序列中初始位置的输入迭代器。
*   `second1`：指定第一序列中结束位置的输入迭代器。
*   `first2`：指定第二序列中初始位置的输入迭代器。
*   `second2`：指定第二序列中结束位置的输入迭代器。
*   `pred`：指定比较谓词（如果指定的话）。

## 返回值

如果两个序列相同，函数返回 `true`，否则返回 `false`。

## 注意

以上功能针对 C++ 14 及以上版本。

## 程序-1

```cpp
// C++ program to implement the
// above mentioned function
#include <bits/stdc++.h>
#include <boost/algorithm/cxx14/equal.hpp>
using namespace std;

// Drivers code
int main()
{
    // Declares the sequences
    int a[] = { 1, 2, 5, 6, 8 };
    int b[] = { 1, 2, 5, 6, 8 };

    // Run the function
    bool ans
        = boost::algorithm::equal(a, a + 5, b, b + 5);

    // Condition to check
    if (ans == 1)
        cout << "Sequence1 and Sequence2 are equal";
    else
        cout << "Sequence1 and Sequence2 are not equal";
    return 0;
}
```

**输出：**

```cpp
Sequence1 and Sequence2 are equal
```

## 程序-2

```cpp
// C++ program to implement the
// above mentioned function
#include <bits/stdc++.h>
#include <boost/algorithm/cxx14/equal.hpp>
using namespace std;

// Drivers code
int main()
{
    // Declares the sequences
    int a[] = { 1, 2, 5, 6, 8 };
    int b[] = { 1, 2, 5 };

    // Run the function
    bool ans
        = boost::algorithm::equal(a, a + 5, b, b + 5);

    // Condition to check
    if (ans == 1)
        cout << "Sequence1 and Sequence2 are equal";
    else
        cout << "Sequence1 and Sequence2 are not equal";
    return 0;
}
```

**输出：**

```cpp
Sequence1 and Sequence2 are not equal
```

## 参考

[https://www.boost.org/doc/libs/1_70_0/libs/algorithm/doc/html/algorithm/CXX14.html#the_boost_algorithm_library.CXX14.equal](https://www.boost.org/doc/libs/1_70_0/libs/algorithm/doc/html/algorithm/CXX14.html#the_boost_algorithm_library.CXX14.equal)