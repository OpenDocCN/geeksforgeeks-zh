# c++ STL 中的 deque resize()函数

> 原文:[https://www . geesforgeks . org/deque-resize-function-in-c-STL/](https://www.geeksforgeeks.org/deque-resize-function-in-c-stl/)

**decue::resize()**是 C++ STL 中的一个内置函数，它改变了 decue 的大小。
如果给定的大小大于当前的大小，那么新元素将被插入到 deque 的末尾。
如果给定的尺寸小于当前尺寸，则多余的元素被破坏。

**语法:**

```cpp
deque_name.resize(n)
```

**参数:**该函数只接受一个强制参数 ***n*** ，该参数指定了德格的大小。

**返回值:**函数不返回任何内容。

下面的程序说明了上面的功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// deque::resize() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    deque<int> dq = { 10, 20, 30, 40, 50 };

    cout << "Size before resize " << dq.size() << "\n";

    // Prints the deque elements
    cout << "The contents of deque :";
    for (auto it = dq.begin(); it != dq.end(); ++ it)
        cout << *it << " ";

    cout << endl;

    // resize to 7
    dq.resize(7);

    // // Prints the deque elements after resize()
    cout << "Size after resize " << dq.size() << "\n";

    cout << "The contents of deque :";
    for (auto it = dq.begin(); it != dq.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
Size before resize 5
The contents of deque :10 20 30 40 50 
Size after resize 7
The contents of deque :10 20 30 40 50 0 0

```

**程序 2:**

```cpp
// C++ program to illustrate the
// deque::resize() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    deque<int> dq = { 10, 20, 30, 40, 50 };

    cout << "Size before resize " << dq.size() << "\n";

    // Prints the deque elements
    cout << "The contents of deque :";
    for (auto it = dq.begin(); it != dq.end(); ++ it)
        cout << *it << " ";

    cout << endl;

    // resize to 3
    dq.resize(3);

    cout << "Size after resize " << dq.size() << "\n";

    cout << "The contents of deque :";
    for (auto it = dq.begin(); it != dq.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
Size before resize 5
The contents of deque :10 20 30 40 50 
Size after resize 3
The contents of deque :10 20 30

```

**时间复杂度:** O(N)