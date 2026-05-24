# 相信 C++ STL

> 原文:[https://www.geeksforgeeks.org/deque-crend-in-c-stl/](https://www.geeksforgeeks.org/deque-crend-in-c-stl/)

**decue::crend()**是 C++ STL 中的一个内置函数，它返回一个**常量**反向迭代器，指向 decue 第一个元素之前的位置。
**语法**

```cpp
deque_name.crend()

```

**参数:**此功能不接受任何参数。
**返回类型:**这个函数返回德格的常量反向迭代器。

**示例-1:**

```cpp
// C++ program to illustrate the
// deque::crend() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    deque<int> dq = { 10, 20, 30, 40, 50 };

    cout << "The deque in reverse order: \n";

    // prints the elements in reverse order
    for (auto it = dq.crend() - 1; it >= dq.crbegin(); --it)
        cout << *it << endl;

    return 0;
}
```

**Output:**

```cpp
The deque in reverse order: 
10
20
30
40
50

```

**示例-2:** 由于迭代器是常量，试图更改它会导致错误。

```cpp
// C++ program to illustrate the
// deque::crend() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    deque<char> dq = { 'a', 'b', 'c', 'd', 'e', 'f' };

    cout << "The deque in reverse order: \n";

    // prints the elements in reverse order
    for (auto it = dq.crend() - 1; it >= dq.crbegin(); --it)
        *it = 'g'

    return 0;
}
```

> CPP 代码中的编译错误:- prog.cpp:在函数“int main()”中:
> prog.cpp:15:13:错误:分配只读位置' it . STD::reverse _ iterator<_iterator>:operator *<:_deque_iterator const="" char="">>()'
> * it = ' g '
> ^
> Prog . CPP:17:5:错误:应为'；''返回'
> 前返回 0；
> ^T9】