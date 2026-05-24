# c++ STL

中的 deque::侵位 _front()和 deque::侵位 _back()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/dequa-place _ front-place _ back-CPP-STL/

[德客](https://www.geeksforgeeks.org/deque-cpp-stl/)或双端队列是两端都有伸缩特征的序列容器。它们类似于向量，但是在末尾和开头插入和删除元素的情况下效率更高。与向量不同，可能无法保证连续的存储分配。

**deque::emplace_front()**

这个函数用于将新的元素插入到 deque 容器中，新的元素被添加到 deque 的开始。
**语法:**

```cpp
*dequename*.emplace_front(*value*)
Parameters :
The element to be inserted into the deque
is passed as the parameter.
Result :
The parameter is added to the
deque at the beginning.

```

示例:

```cpp
Input  : mydeque{1, 2, 3, 4, 5};
         mydeque.emplace_front(6);
Output : mydeque = 6, 1, 2, 3, 4, 5

Input  : mydeque{};
         mydeque.emplace_front(4);
Output : mydeque = 4

```

**错误和异常**
1。它有很强的异常保证，因此，如果抛出异常，不会进行任何更改。
2。参数应该与容器的类型相同，否则会引发错误。

```cpp
// INTEGER DEQUE EXAMPLE
// CPP program to illustrate
// Implementation of emplace_front() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<int> mydeque;
    mydeque.emplace_front(1);
    mydeque.emplace_front(2);
    mydeque.emplace_front(3);
    mydeque.emplace_front(4);
    mydeque.emplace_front(5);
    mydeque.emplace_front(6);

    // deque becomes 6, 5, 4, 3, 2, 1

    // printing the deque
    for (auto it = mydeque.begin();
         it != mydeque.end(); ++ it)
        cout << ' ' << *it;

    return 0;
}
```

输出:

```cpp
6 5 4 3 2 1

```

```cpp
// STRING DEQUE EXAMPLE
// CPP program to illustrate
// Implementation of emplace_front() function
#include <deque>
#include <iostream>
#include <string>
using namespace std;

int main()
{
    deque<string> mydeque;
    mydeque.emplace_front("portal");
    mydeque.emplace_front("science");
    mydeque.emplace_front("computer");
    mydeque.emplace_front("a");
    mydeque.emplace_front("is");
    mydeque.emplace_front("GEEKSFORGEEKS");

    // deque becomes GEEKSFORGEEKS, is, a,
    // computer, science, portal

    // printing the deque
    for (auto it = mydeque.begin();
                  it != mydeque.end(); ++ it)
        cout << ' ' << *it;

    return 0;
}
```

输出:

```cpp
GEEKSFORGEEKS is a computer science portal

```

**时间复杂度:** O(1)

**应用**
给定一个空的 deque，使用侵位 _front()函数向其添加整数，然后不使用 size 函数()计算其大小。

```cpp
Input  : 1, 2, 3, 4, 5, 6
Output : 6
```

**算法**
1。使用定位 _ 前()功能
2 将元素添加到 deque。检查 deque 是否为空，如果不是，递增初始化为 0 的计数器变量，并弹出 back 元素。
3。重复此步骤，直到 deque 变空。
4。打印变量的最终值。

```cpp
// CPP program to illustrate
// Application of emplace_front() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    // variable declaration
    int count = 0;

    // deque declaration
    deque<int> mydeque;

    // adding elements to deque
    mydeque.emplace_front(1);
    mydeque.emplace_front(2);
    mydeque.emplace_front(3);
    mydeque.emplace_front(4);
    mydeque.emplace_front(5);
    mydeque.emplace_front(6);

    // counting elements in deque
    while (!mydeque.empty()) {
        count++ ;
        mydeque.pop_back();
    }
    cout << count;
    return 0;
}
```

输出:

```cpp
6
```

**deque::emplace_back()**

这个函数用于将新的元素插入到 deque 容器中，新的元素被添加到 deque 的末尾。
**语法:**

```cpp
*dequename*.emplace_back(*value*)
Parameters :
The element to be inserted into the deque
is passed as the parameter.
Result :
The parameter is added to the
deque at the end.

```

示例:

```cpp
Input  : mydeque{1, 2, 3, 4, 5};
         mydeque.emplace_back(6);
Output : mydeque = 1, 2, 3, 4, 5, 6

Input  : mydeque{};
         mydeque.emplace_back(4);
Output : mydeque = 4

```

**错误和异常**
1。它有很强的异常保证，因此，如果抛出异常，不会进行任何更改。
2。参数应该与容器的类型相同，否则会引发错误。

```cpp
// INTEGER DEQUE EXAMPLE
// CPP program to illustrate
// Implementation of emplace_back() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<int> mydeque;
    mydeque.emplace_back(1);
    mydeque.emplace_back(2);
    mydeque.emplace_back(3);
    mydeque.emplace_back(4);
    mydeque.emplace_back(5);
    mydeque.emplace_back(6);
    // deque becomes 1, 2, 3, 4, 5, 6

    // printing the deque
    for (auto it = mydeque.begin();
             it != mydeque.end(); ++ it)
        cout << ' ' << *it;

    return 0;
}
```

输出:

```cpp
1 2 3 4 5 6

```

```cpp
// STRING DEQUE EXAMPLE
// CPP program to illustrate
// Implementation of emplace_back() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<string> mydeque;
    mydeque.emplace_back("Hi");
    mydeque.emplace_back("this");
    mydeque.emplace_back("is");
    mydeque.emplace_back("geeksforgeeks");
    // deque becomes Hi this is geeksforgeeks

    // printing the deque
    for (auto it = mydeque.begin();
                it != mydeque.end(); ++ it)
        cout << ' ' << *it;

    return 0;
}
```

输出:

```cpp
Hi this is geeksforgeeks

```

**时间复杂度:** O(1)
**应用**
给定一个空的 deque，使用侵位 _front()函数向其添加整数，然后计算元素的和。

```cpp
Input  : 4, 5, 9, 2, 6
Output : 26
```

**算法**
1。使用定位 _ 后退()功能
2 将元素添加到目标。检查 deque 是否为空，如果不是，将 back 值添加到初始化为 0 的 sum 变量中，并弹出 back 元素。
3。重复此步骤，直到 deque 变空。
4。打印变量的最终值。

```cpp
// CPP program to illustrate
// Application of emplace_back() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    // variable declaration
    int sum = 0;

    // deque declaration
    deque<int> mydeque;

    // adding elements to deque
    mydeque.emplace_back(4);
    mydeque.emplace_back(5);
    mydeque.emplace_back(9);
    mydeque.emplace_back(2);
    mydeque.emplace_back(6);

    // counting sum of elements in deque
    while (!mydeque.empty()) {
        sum = sum + mydeque.back();
        mydeque.pop_back();
    }
    cout << sum;
    return 0;
}
```

输出:

```cpp
6
```