# boost::算法::C++ 库中的 all_of_equal()

> 原文:[https://www . geeksforgeeks . org/boostalgorithmall _ of _ equal-in-c-library/](https://www.geeksforgeeks.org/boostalgorithmall_of_equal-in-c-library/)

**[C++ boost 库](https://www.geeksforgeeks.org/advanced-c-boost-library/)** 中的 **all_of_equal()** 函数位于标题*“boost/algorithm/cxx 11/all _ of . HPP”*下，该函数根据参数中传递的值测试序列的所有元素，如果序列的所有元素都相同，则返回 true。它接受一个序列和值，如果序列中的所有元素都相同，则返回 true。

**语法**:

> bool all_of_equal(输入运算符第一个，输入运算符最后一个，常量&value)
> 或
> bool all_of_equal(常量范围& R，常量&值)

**参数**:该功能接受如下参数:

*   **第一个**:指定序列中初始位置的输入迭代器。
*   **秒**:指定序列中最后位置的输入迭代器。
*   **值**:指定序列中所有元素的检查值。
*   **R** :是完整的序列。

**返回值**:如果序列的所有元素都等于值，则函数返回 true，否则返回 false。

下面是上述方法的实现:

**程序-1** :

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

**程序-2** :

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

**参考**:[https://www . boost . org/doc/libs/1 _ 70 _ 0/libs/algorithm/doc/html/algorithm/cxx 11 . html # the _ boost _ algorithm _ library。CXX11.all_of](https://www.boost.org/doc/libs/1_70_0/libs/algorithm/doc/html/algorithm/CXX11.html#the_boost_algorithm_library.CXX11.all_of)