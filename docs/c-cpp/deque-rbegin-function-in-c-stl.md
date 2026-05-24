# c++ STL 中的 deque rbegin()函数

> 原文:[https://www . geesforgeks . org/deque-rbe gin-function-in-c-STL/](https://www.geeksforgeeks.org/deque-rbegin-function-in-c-stl/)

**decue::rbe gin()**是 C++ STL 中的一个内置函数，它返回一个*反向迭代器*，该迭代器指向 decue 的最后一个元素(即它的反向开始)。

**语法:**

```cpp
deque_name.rbegin()
```

**参数:**此功能不接受任何参数。

**返回值:**它返回一个*反向迭代器*，该迭代器指向 deque 的最后一个元素。

下面的程序说明了上面的功能:
**程序 1:**

```cpp
// C++ program to illustrate the
// deque::rbegin() function
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
// deque::rbegin() function
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