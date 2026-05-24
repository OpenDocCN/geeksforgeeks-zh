# `boost::algorithm::C++` 库中的 `all_of_equal()`

> 原文：[https://www.geeksforgeeks.org/boostalgorithmall_of_equal-in-c-library/](https://www.geeksforgeeks.org/boostalgorithmall_of_equal-in-c-library/)

[`C++ boost 库`](https://www.geeksforgeeks.org/advanced-c-boost-library/) 中的 `all_of_equal()` 函数位于头文件 `"boost/algorithm/cxx11/all_of.hpp"` 下。该函数根据参数中传递的值测试序列的所有元素，如果序列的所有元素都相同，则返回 `true`。它接受一个序列和值，如果序列中的所有元素都相同，则返回 `true`。

## 语法

> `bool all_of_equal(InputIterator first, InputIterator last, const T& value)`
> 或
> `bool all_of_equal(const Range& r, const T& value)`

## 参数

该函数接受如下参数：

*   `first`：指定序列中初始位置的输入迭代器。
*   `last`：指定序列中最后位置的输入迭代器。
*   `value`：指定序列中所有元素的检查值。
*   `r`：是完整的序列。

## 返回值

如果序列的所有元素都等于 `value`，则函数返回 `true`，否则返回 `false`。

下面是上述方法的实现：

### 程序-1

```cpp
// C++ program to implement the
// above mentioned function

#include <bits/stdc++.h>
#include <boost/algorithm/cxx11/all_of.hpp>
using namespace std;

// Drivers code
int main()
{

    // Declares the sequence with
    // 5 length and all elements as 1
    // [1, 1, 1, 1, 1]
    vector<int> c(5, 1);

    // Run the function
    bool ans
        = boost::algorithm::all_of_equal(c, 1);

    // Condition to check
    if (ans == 1)
        cout << "ALl elements are 1";
    else
        cout << "All elements are not 1";
    return 0;
}
```

**Output:**

```cpp
ALl elements are 1
```

### 程序-2

```cpp
// C++ program to implement the
// above mentioned function

#include <bits/stdc++.h>
#include <boost/algorithm/cxx11/all_of.hpp>
using namespace std;

// Drivers code
int main()
{

    // Declares the sequence
    int a[] = { 1, 2, 5, 6 };

    // Run the function
    bool ans
        = boost::algorithm::all_of_equal(a, a + 4, 4);

    // Condition to check
    if (ans == 1)
        cout << "ALl elements are 4";
    else
        cout << "All elements are not 4";
    return 0;
}
```

**Output:**

```cpp
All elements are not 4
```

**参考**：[https://www.boost.org/doc/libs/1_70_0/libs/algorithm/doc/html/algorithm/CXX11.html#the_boost_algorithm_library.CXX11.all_of](https://www.boost.org/doc/libs/1_70_0/libs/algorithm/doc/html/algorithm/CXX11.html#the_boost_algorithm_library.CXX11.all_of)