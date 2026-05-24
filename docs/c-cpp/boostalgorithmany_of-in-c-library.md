# boost::算法::C++ 库中的任意 _of()

> 原文:[https://www . geeksforgeeks . org/boostalgorithmulti _ of-in-c-library/](https://www.geeksforgeeks.org/boostalgorithmany_of-in-c-library/)

**[C++ boost 库](https://www.geeksforgeeks.org/advanced-c-boost-library/)** 中的 **any_of()** 函数位于标题*“boost/algorithm/cxx 11/any _ of . HPP”*下，该函数测试序列的元素，如果其中任何元素共享给定的属性，则返回 true。它接受一个序列和一个谓词，如果谓词为序列中的任何给定元素返回 true，则返回 true。

**语法**:

> bool any_of(输入符在前，输入符在后，谓词 p )
> 或
> bool any_of(常量范围& R，谓词 p)

**参数**:该功能接受如下参数:

*   **第一个**:指定序列中初始位置的输入迭代器。
*   **秒**:指定序列中最后位置的输入迭代器。
*   **p** :指定接受一个元素并返回 bool 的一元谓词函数。
*   **R** :是完整的序列。

**返回值**:如果给定的谓词在序列的任何元素上为真，则函数返回真，否则返回假。

下面是上述方法的实现:

**程序-1** :

```cpp
// C++ program to implement the
// above mentioned function

#include <bits/stdc++.h>
#include <boost/algorithm/cxx11/any_of.hpp>
using namespace std;
// using boost::algorithm;

// Predicate function to check if
// the element is odd or not
bool isOdd(int i)
{
    return i % 2 == 1;
}

// Drivers code
int main()
{

    // Declares the sequence
    int c[] = { 1, 2, 3 };

    // Run the function with second syntax
    bool ans = boost::algorithm::any_of(c, isOdd);

    // Condition to check
    if (ans == 1)
        cout << "at least one element is odd";
    else
        cout << "all elements are even";
    return 0;
}
```

**Output:**

```cpp
at least one element is odd

```

**程序-2** :

```cpp
// C++ program to implement the
// above mentioned function

#include <bits/stdc++.h>
#include <boost/algorithm/cxx11/any_of.hpp>
using namespace std;
// using boost::algorithm;

// Predicate function to check if
// the elements are less than 7 or not
bool anyLessThanSeven(int i)
{
    return i < 7;
}

// Drivers code
int main()
{

    // Declares the sequence
    int a[] = { 1, 2, 10, 8 };

    // Run the function with first syntax
    bool ans
        = boost::algorithm::any_of(a, a + 4,
                                   anyLessThanSeven);

    // Condition to check
    if (ans == 1)
        cout << "at least one element is less than 7";
    else
        cout << "all elements are not less than 7";
    return 0;
}
```

**Output:**

```cpp
at least one element is less than 7

```

**参考**:[https://www . boost . org/doc/libs/1 _ 70 _ 0/libs/algorithm/doc/html/the _ boost _ algorithm _ library/CXX11/any _ of . html](https://www.boost.org/doc/libs/1_70_0/libs/algorithm/doc/html/the_boost_algorithm_library/CXX11/any_of.html)