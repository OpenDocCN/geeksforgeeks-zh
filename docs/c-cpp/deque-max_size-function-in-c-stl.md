# c++ STL 中的 deque max_size()函数

> 原文:[https://www . geesforgeks . org/deque-max _ size-function-in-c-STL/](https://www.geeksforgeeks.org/deque-max_size-function-in-c-stl/)

**deque::max_size()** 是 C++ STL 中的内置函数，返回一个 deque 容器可以容纳的最大元素数。

**语法:**

```cpp
deque_name.max_size()
```

**参数:**函数不接受任何参数。

**返回值:**函数返回一个 deque 容器可以容纳的最大元素数。

以下程序说明了上述功能:

**程序 1:**

```cpp
// CPP program to demonstrate the
// deque::max_size() function
// when deque is non-empty
#include <bits/stdc++.h>
using namespace std;
int main()
{
    deque<int> dq;

    dq.push_back(1);
    dq.push_back(10);
    dq.push_back(100);
    dq.push_back(50);
    dq.push_back(40);
    dq.push_back(23);
    dq.push_back(6);

    cout << "The deque elements: ";
    for (auto it = dq.begin(); it != dq.end(); it++)
        cout << *it << " ";

    cout << "\nThe max-size of deque: " << dq.max_size();

    return 0;
}
```

**Output:**

```cpp
The deque elements: 1 10 100 50 40 23 6 
The max-size of deque: 4611686018427387903

```

**程序 2:**

```cpp
// CPP program to demonstrate the
// deque::max_size() function
// when deque is empty
#include <bits/stdc++.h>
using namespace std;
int main()
{
    deque<int> dq;

    cout << "The max-size of deque: " << dq.max_size();

    return 0;
}
```

**Output:**

```cpp
The max-size of deque: 4611686018427387903

```