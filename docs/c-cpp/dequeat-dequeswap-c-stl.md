# c++ STL 中的 deque::at()和 deque::swap()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/dequiate-dequietw WAP-c-STL/

[德客](https://www.geeksforgeeks.org/deque-cpp-stl/)或双端队列是具有两端伸缩特性的序列容器。它们类似于向量，但是在末尾和开头插入和删除元素的情况下效率更高。与向量不同，可能无法保证连续的存储分配。

**deque::at()**

at()函数用于引用出现在 ***位置*** 的元素，该位置作为函数的参数给出。
**语法:**

```cpp
*dequename*.at(***position***)
Parameters :
Position of the element to be fetched.
Returns :
Direct reference to the element at the given position.

```

示例:

```cpp
Input  :  mydeque = 1, 2, 3
          mydeque.at(2);
Output :  3

Input  :  mydeque = 3, 4, 1, 7, 3
          mydeque.at(3);
Output :  7

```

**错误和异常**

1.如果该位置不在德格中，它会将 ***抛出范围外*** 。
2。否则，它具有很强的无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of at() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<int> mydeque;
    mydeque.push_back(3);
    mydeque.push_back(4);
    mydeque.push_back(1);
    mydeque.push_back(7);
    mydeque.push_back(3);
    cout << mydeque.at(3);
    return 0;
}
```

输出:

```cpp
7

```

**应用程序**
给定一个整数序列，打印偶数位置的所有整数。

```cpp
Input  :1, 2, 3, 4, 5, 6, 7, 8, 9
Output :1 3 5 7 9
*Explanation - 1, 3, 5, 7 and 9 are at position 0, 2, 4, 6 and 8 which are even*

```

**算法**
1。运行一个循环，直到数组的大小。
2。检查该位置是否可被 2 整除，如果是，打印该位置的元素。

```cpp
// CPP program to illustrate
// Application of at() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<int> mydeque;
    mydeque.push_back(1);
    mydeque.push_back(2);
    mydeque.push_back(3);
    mydeque.push_back(4);
    mydeque.push_back(5);
    mydeque.push_back(6);
    mydeque.push_back(7);
    mydeque.push_back(8);
    mydeque.push_back(9);
    // Deque becomes 1, 2, 3, 4, 5, 6, 7, 8, 9

    for (int i = 0; i < mydeque.size(); ++ i) {
        if (i % 2 == 0) {
            cout << mydeque.at(i);
            cout << " ";
        }
    }
    return 0;
}
```

输出:

```cpp
1 3 5 7 9

```

**deque::swap()**

此功能用于将一个 deque 的内容与另一个相同类型和大小的 deque 进行交换。

**语法:**

```cpp
*dequename1*.swap(*dequename2*)
Parameters :
The name of the deque with which
the contents have to be swapped.
Result :
All the elements of the 2 deque are swapped.

```

示例:

```cpp
Input  : mydeque1 = {1, 2, 3, 4}
         mydeque2 = {3, 5, 7, 9}
         mydeque1.swap(mydeque2);
Output : mydeque1 = {3, 5, 7, 9}
         mydeque2 = {1, 2, 3, 4}

Input  : mydeque1 = {1, 3, 5, 7}
         mydeque2 = {2, 4, 6, 8}
         mydeque1.swap(mydeque2);
Output : mydeque1 = {2, 4, 6, 8}
         mydeque2 = {1, 3, 5, 7}

```

**错误和异常**

1.如果 deque 不是同一类型，它将引发错误。
2。如果 deque 大小不同，它会抛出错误。
2。否则它有一个基本的无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of swap() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    // deque container declaration
    deque<int> mydeque1{ 1, 2, 3, 4 };
    deque<int> mydeque2{ 3, 5, 7, 9 };

    // using swap() function to swap elements of deques
    mydeque1.swap(mydeque2);

    // printing the first deque
    cout << "mydeque1 = ";
    for (auto it = mydeque1.begin(); it < mydeque1.end(); ++ it)
        cout << *it << " ";

    // printing the second deque
    cout << endl
         << "mydeque2 = ";
    for (auto it = mydeque2.begin(); it < mydeque2.end(); ++ it)
        cout << *it << " ";
    return 0;
}
```

输出:

```cpp
mydeque1 = 3 5 7 9 
mydeque2 = 1 2 3 4 

```