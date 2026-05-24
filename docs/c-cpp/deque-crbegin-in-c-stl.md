# c++ STL 中的 crbegin

> 原文:[https://www.geeksforgeeks.org/deque-crbegin-in-c-stl/](https://www.geeksforgeeks.org/deque-crbegin-in-c-stl/)

**deque::crbegin** 的意思是 constant _ reverse _ 初学者，顾名思义，它返回一个指向 deque 最后一个元素的 constant_reverse_iterator。

**什么是常数迭代器？**
常量迭代器不用于修改。它仅用于访问元素。您可以使用非常数迭代器来修改元素。

**语法:**

```cpp
dequename.crbegin()
```

**返回值:**返回一个 const_reverse_iterator 到序列的反向开始。

**应用:**

> 给定一个以递增顺序排列的数字，以非递增顺序打印它们。
> **输入:**德格{1，2，3，4，5，6 }；
> **为(auto reverse it = deque . crbegin()；逆转！= deque . crend()；++ reverse it)
> cout<<' '<<* reverse it；**
> **输出** : 6 5 4 3 2 1

下面的程序说明了 crbegin 函数的工作原理:

```cpp
// deque::crbegin and crend
#include <deque>
#include <iostream>
using namespace std;
int main()
{
    // Declare a deque with the name numdeque
    deque<int> numdeque = { 1, 2, 3, 4, 5, 6 };

    // Print the deque backwards using crbegin and crend
    cout << "Printing the numdeque backwards:";

    for (auto rit = numdeque.crbegin(); rit != numdeque.crend(); ++ rit)
        cout << ' ' << *rit;

    return 0;
}
```

**Output:**

```cpp
Printing the numdeque backwards: 6 5 4 3 2 1

```

由于返回的迭代器是常量，如果我们试图改变值，我们会得到编译器错误。

```cpp
// deque::crbegin and crend
#include <deque>
#include <iostream>
using namespace std;
int main()
{
    // Declare a deque with the name numdeque
    deque<int> numdeque = { 1, 2, 3, 4, 5, 6 };

    // Print the deque backwards using crbegin and crend
    cout << "Printing the numdeque backwards:";

    for (auto rit = numdeque.crbegin(); rit != numdeque.crend(); ++ rit)
         *rit = 10;

    return 0;
}
```

输出:

> **prog.cpp:** 在函数“int main()”中:
> **prog.cpp:14:8:错误:**赋值只读位置“rit . STD::reverse _ iterator<_iterator>:operator *<:_deque_iterator const="" int="">>()”
> * rit = 10；
> ^T10】