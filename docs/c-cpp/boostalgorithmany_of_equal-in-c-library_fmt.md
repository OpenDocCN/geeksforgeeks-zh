# boost::algorithm::C++ 库中的 `any_of_equal()`

> 原文：[https://www.geeksforgeeks.org/boostalgorithmany_of_equal-in-c-library/](https://www.geeksforgeeks.org/boostalgorithmany_of_equal-in-c-library/)

[C++ boost 库](https://www.geeksforgeeks.org/advanced-c-boost-library/) 中的 `any_of_equal()` 函数位于头文件 `"boost/algorithm/cxx11/any_of.hpp"` 下。该函数根据传递的值测试序列中的任何元素是否相同。它接受一个序列和值，如果序列中的任何元素与传递的值相同，则返回 `true`。

## 语法

```cpp
bool any_of_equal(InputIterator first, InputIterator last, const T& value)
// 或
bool any_of_equal(const Range& R, const T& value)
```

## 参数

该函数接受如下参数：

*   `first`：指定序列中初始位置的输入迭代器。
*   `last`：指定序列中最后位置的输入迭代器。
*   `value`：它指定了一个值，该值将针对序列的任何元素进行检查。
*   `R`：是完整的序列。

## 返回值

如果序列中有任何元素等于 `value`，则函数返回 `true`，否则返回 `false`。

下面是上述方法的实现：

### 程序-1

```cpp
// C++ program to implement the
// above mentioned function

#include <bits/stdc++.h>
#include <boost/algorithm/cxx11/any_of.hpp>
using namespace std;

// Drivers code
int main()
{

    // Declares the sequence with
    int c[] = { 1, 2, 3 };

    // Run the function
    bool ans
        = boost::algorithm::any_of_equal(c, 1);

    // Condition to check
    if (ans == 1)
        cout << "at least one elements is 1";
    else
        cout << "all elements are not 1";
    return 0;
}
```

**Output:**

```cpp
at least one elements is 1
```

### 程序-2

```cpp
// C++ program to implement the
// above mentioned function

#include <bits/stdc++.h>
#include <boost/algorithm/cxx11/any_of.hpp>
using namespace std;

// Drivers code
int main()
{

    // Declares the sequence
    int a[] = { 1, 2, 3, 6 };

    // Run the function
    bool ans
        = boost::algorithm::any_of_equal(a, a + 4, 4);

    // Condition to check
    if (ans == 1)
        cout << "at least one element is 4";
    else
        cout << "all elements are not 4";
    return 0;
}
```

**Output:**

```cpp
all elements are not 4
```

## 参考

[https://www.boost.org/doc/libs/1_70_0/libs/algorithm/doc/html/the_boost_algorithm_library/CXX11/any_of.html](https://www.boost.org/doc/libs/1_70_0/libs/algorithm/doc/html/the_boost_algorithm_library/CXX11/any_of.html)