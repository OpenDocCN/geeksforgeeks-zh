# c++ STL 中的 deque::begin()和 deque::end

> 哎哎哎:# t0]https://www . geeksforgeeks . org/dequebegin-dequeend-c-STL/

[德客](https://www.geeksforgeeks.org/deque-cpp-stl/)或双端队列是具有两端伸缩特性的序列容器。它们类似于向量，但是在末尾和开头插入和删除元素的情况下效率更高。与向量不同，可能无法保证连续的存储分配。

**deque::begin()**

begin()函数用于返回指向 deque 容器第一个元素的迭代器。begin()函数**返回一个双向迭代器**到容器的第一个元素。

**语法:**

```cpp
*dequename*.begin()
Parameters :
No parameters are passed.
Returns :
This function returns a bidirectional
iterator pointing to the first element.

```

示例:

```cpp
Input  : mydeque{1, 2, 3, 4, 5};
         mydeque.begin();
Output : *returns an iterator to the element 1*

Input  : mydeque{8, 7};
         mydeque.begin();
Output : *returns an iterator to the element 8*

```

**错误和异常**

1.它有一个无异常抛出保证。
2。传递参数时显示错误。

```cpp
// CPP program to illustrate
// Implementation of begin() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    // declaration of deque container
    deque<int> mydeque{ 1, 2, 3, 4, 5 };

    // using begin() to print deque
    for (auto it = mydeque.begin(); it != mydeque.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
1 2 3 4 5

```

**时间复杂度:** O(1)

**deque::end()**

end()函数用于返回指向 deque 容器最后一个元素的迭代器。end()函数**返回一个双向迭代器**到容器的最后一个元素。
注意:任何容器的最后一个元素被认为是容器中存储的最后一个值旁边的理论元素。

**语法:**

```cpp
*dequename*.end()
Parameters :
No parameters are passed.
Returns :
This function returns a bidirectional
iterator pointing to the last element.

```

示例:

```cpp
Input  : mydeque{1, 2, 3, 4, 5};
         mydeque.end();
Output : *returns an iterator to the element next to the element 5*

Input  : mydeque{8, 7};
         mydeque.end();
Output : *returns an iterator to the element next to the element 7*

```

**错误和异常**

1.它有一个无异常抛出保证。
2。传递参数时显示错误。

```cpp
// CPP program to illustrate
// Implementation of end() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    // declaration of deque container
    deque<int> mydeque{ 1, 2, 3, 4, 5 };

    // using end() to print deque
    for (auto it = mydeque.begin(); it != mydeque.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
1 2 3 4 5

```

**时间复杂度:** O(1)