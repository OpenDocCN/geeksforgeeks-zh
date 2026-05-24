# c++ STL 中的 deque rend()函数

> 原文:[https://www.geeksforgeeks.org/deque-rend-function-in-c-stl/](https://www.geeksforgeeks.org/deque-rend-function-in-c-stl/)

**反求::rend()** 是 C++ STL 中的一个内置函数，它返回一个*反向迭代器*，该迭代器指向反求开始之前的位置(这被认为是它的反向结束)。

**语法:**

```cpp
deque_name.rend()
```

**参数:**此功能不接受任何参数。

**返回值:**返回一个*反向迭代器*，该迭代器指向德格开始前的位置。

下面的程序说明了上面的功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// deque::rend() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    deque<int> dq = { 10, 20, 30, 40, 50 };

    cout << "The deque in reverse order: ";

    // prints the elements in reverse order
    for (auto it = dq.rbegin(); it != dq.rend(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
The deque in reverse order: 50 40 30 20 10

```

**程序 2:**

```cpp
// C++ program to illustrate the
// deque::rend() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    deque<char> dq = { 'a', 'b', 'c', 'd', 'e' };

    cout << "The deque in reverse order: ";

    // prints the elements in reverse order
    for (auto it = dq.rbegin(); it != dq.rend(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
The deque in reverse order: e d c b a

```