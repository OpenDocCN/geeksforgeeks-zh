# boost::算法::C++ 库中的 none_of_equal()

> 原文:[https://www . geeksforgeeks . org/boostalgorithmnone _ of _ equal-in-c-library/](https://www.geeksforgeeks.org/boostalgorithmnone_of_equal-in-c-library/)

**[C++ boost 库](https://www.geeksforgeeks.org/advanced-c-boost-library/)** 中的 **none_of_equal()** 函数位于标题*'**boost/algorithm/cxx 11/none _ of . HPP**'*下，该函数根据参数中传递的值测试序列的所有元素，如果序列的所有元素都不等于传递的值，则返回 true。它接受一个序列和值，如果序列中没有元素等于该值，则返回 true。

**语法**:

> bool non _ of _ equal(输入运算符第一个，输入运算符最后一个，常量&value)
> 或
> bool non _ of _ equal(常量范围& R，常量&值)

**参数**:该功能接受如下参数:

*   **第一个**:指定序列中初始位置的输入迭代器。
*   **秒**:指定序列中最后位置的输入迭代器。
*   **值**:它指定了一个值，该值将针对序列中的任何元素进行检查。
*   **R** :是完整的序列。

**返回值**:如果序列中没有一个元素等于值，则函数返回真，否则返回假。

下面是上述方法的实现:

**程序-1** :

```cpp
// C++ program to implement the
// above mentioned function

#include <bits/stdc++.h>
#include <boost/algorithm/cxx11/none_of.hpp>
using namespace std;

// Drivers code
int main()
{

    // Declares the sequence with
    // 5 length and none elements as 1
    // [1, 1, 1, 1, 1]
    vector<int> c(5, 1);

    // Run the function
    bool ans
        = boost::algorithm::none_of_equal(c, 1);

    // Condition to check
    if (ans == 1)
        cout << "all not equal to 1";
    else
        cout << "all equals to 1";
    return 0;
}
```

**Output:**

```cpp
all equals to 1

```

**程序-2** :

```cpp
// C++ program to implement the
// above mentioned function

#include <bits/stdc++.h>
#include <boost/algorithm/cxx11/none_of.hpp>
using namespace std;

// Drivers code
int main()
{

    // Declares the sequence
    int a[] = { 1, 2, 5, 6 };

    // Run the function
    bool ans
        = boost::algorithm::none_of_equal(a, a + 4, 4);

    // Condition to check
    if (ans == 1)
        cout << "all not equal to 4";
    else
        cout << "all equal to 4";
    return 0;
}
```

**Output:**

```cpp
all not equal to 4

```

**参考**:[https://www . boost . org/doc/libs/1 _ 70 _ 0/libs/algorithm/doc/html/the _ boost _ algorithm _ library/CXX11/none _ of . html](https://www.boost.org/doc/libs/1_70_0/libs/algorithm/doc/html/the_boost_algorithm_library/CXX11/none_of.html)