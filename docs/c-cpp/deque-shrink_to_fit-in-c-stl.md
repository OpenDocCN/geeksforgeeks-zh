# 德克尔在 C++ STL 中收缩到适合

> 原文:[https://www.geeksforgeeks.org/deque-shrink_to_fit-in-c-stl/](https://www.geeksforgeeks.org/deque-shrink_to_fit-in-c-stl/)

**[deque](https://www.geeksforgeeks.org/deque-set-1-introduction-applications/):shrink _ to _ fit()**是 C++ STL 中的一个内置函数，它会减少容器的容量以适合其大小，并销毁超出容量的所有元素。该功能不会减小容器的尺寸。当一个容器被分配了比它所需要的更多的内存，那么这个函数就释放了额外分配的内存量。

**语法:**

```cpp
deque_name.shrink_to_fit()

```

**参数:**此功能不接受任何参数。
**返回值:**函数不返回任何内容。

以下程序说明了上述功能:
**示例-1**

```cpp
// C++ program to illustrate
// the deque::shrink_to_fit()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initialized deque
    deque<int> d(10);

    for (int i = 0; i < 5; i++)
        d[i] = i;

    // Initial deque
    cout << " Deque size initially: " << d.size();

    cout << "\n Deque  elements are: ";
    for (int i = 0; i < 10; i++)
        cout << d[i] << " ";

    // changes the size of the Deque
    // but does not destroys the elements
    d.resize(7);

    cout << "\n Deque size after resize(7): "
         << d.size();

    cout << "\n Deque elements after resize(7) are: ";
    for (int i = 0; i < 10; i++)
        cout << d[i] << " ";

    // Shrinks to the size
    // till which elements are
    // destroys the elements after 5
    d.shrink_to_fit();

    cout << "\n Deque size after shrink_to_fit(): "
         << d.size();

    cout << "\n Deque elements after shrink_to_fit() are: ";
    for (int i = 0; i < 10; i++)
        cout << d[i] << " ";

    return 0;
}
```

**Output:**

```cpp
Deque size initially: 10
Deque  elements are: 0 1 2 3 4 0 0 0 0 0 
Deque size after resize(7): 7
Deque elements after resize(7) are: 0 1 2 3 4 0 0 0 0 0 
Deque size after shrink_to_fit(): 7
Deque elements after shrink_to_fit() are: 0 1 2 3 4 0 0 0 0 0

```

**示例-2**

```cpp
// C++ program to illustrate
// the deque::shrink_to_fit()
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // creating a deque
    deque<int> d(100);

    cout << "Size of d is : " << d.size() << endl;

    // resizing
    d.resize(20);

    cout << "Size of d after resize is : " << d.size() << endl;

    d.shrink_to_fit();
    return 0;
}
```

**Output:**

```cpp
Size of d is : 100
Size of d after resize is : 20

```

**注意:**在向量中容器大小流畅变化的情况下，shrink_to_fit()函数非常有用。