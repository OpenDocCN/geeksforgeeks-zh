# c++ STL 中的 deque::clear()和 deque::erase()

> 原文:[https://www.geeksforgeeks.org/dequeclear-dequeerase-c-stl/](https://www.geeksforgeeks.org/dequeclear-dequeerase-c-stl/)

[德客](https://www.geeksforgeeks.org/deque-cpp-stl/)或双端队列是具有两端伸缩特性的序列容器。它们类似于向量，但是在末尾和开头插入和删除元素的情况下效率更高。与向量不同，可能无法保证连续的存储分配。

**deque::clear()**

clear()函数用于移除 deque 容器的所有元素，从而使其大小为 0。
**语法:**

```cpp
***dequename.clear()***
Parameters :
No parameters are passed.
Result :
All the elements of the deque are
removed ( or destroyed )
```

示例:

```cpp
Input  : mydeque = {1, 2, 3, 4, 5}
         mydeque.clear();
Output : mydeque = {}

Input  : mydeque = {}
         mydeque.clear();
Output : mydeque = {}
```

**错误和异常**
1。它有一个无异常抛出保证。
2。传递参数时显示错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of clear() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<int> mydeque{ 1, 2, 3, 4, 5 };

    mydeque.clear();
    // Deque becomes empty

    // Printing the deque
    for (auto it = mydeque.begin(); it != mydeque.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
*No Output*
```

**deque::erase()**

erase()函数用于从指定位置或范围移除容器中的元素。
**语法:**

```cpp
1\. ***dequename.erase(position)***
2\. ***dequename.erase(startingposition, endingposition)***
Parameters :
Position of the element to be removed in the form of iterator.
or the range specified using start and end iterator.
Result :
Elements are removed from the specified
position of the container.
```

示例:

```cpp
Input  : mydeque{1, 2, 3, 4, 5}, iterator= 2
         mydeque.erase(iterator);
Output : 1, 2, 4, 5

Input  : mydeque{1, 2, 3, 4, 5, 6, 7, 8}, iterator1= 3, iterator2= 6
         mydeque.erase(iterator1, iterator2);
Output : 1, 2, 3, 8
```

**错误和异常**
1。如果位置有效，它有一个无异常抛出保证。
2。否则显示未定义的行为。
**从特定位置移除元素**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of erase() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<int> mydeque{ 1, 2, 3, 4, 5 };
    deque<int>::iterator it;

    it = mydeque.begin();
    mydeque.erase(it);

    // Printing the deque
    for (auto it = mydeque.begin(); it != mydeque.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
2 3 4 5
```

**移除范围内的元素**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of erase() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<int> mydeque{ 1, 2, 3, 4, 5 };
    deque<int>::iterator it1, it2;

    it1 = mydeque.begin();
    it2 = mydeque.end();
    it2--;
    it2--;

    mydeque.erase(it1, it2);

    // Printing the deque
    for (auto it = mydeque.begin(); it != mydeque.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
4 5
```

**应用程序**
给定一个整数列表，从德格中移除所有偶数元素并打印德格。

```cpp
Input  :1, 2, 3, 4, 5, 6, 7, 8, 9
Output :1 3 5 7 9
*Explanation - 2, 4, 6 and 8 which are even are erased from the deque*
```

**算法**
1。运行一个循环，直到德奎的大小。
2。检查每个位置的元素是否可以被 2 整除，如果可以，移除元素并增加迭代器，否则只增加迭代器来检查下一个元素。
3。打印最终质量。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Application of erase() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<int> mydeque{ 1, 2, 3, 4, 5, 6, 7, 8, 9 };
    deque<int>::iterator i;
    i = mydeque.begin();
    while (i != mydeque.end()) {
        if (*i % 2 == 0)     
 /* Not a good idea to erase inside loop, if you delete last element,
 mydeque.end() cannot be found resulting in infinite loop */
            mydeque.erase(i);
        i++ ;       
    }

    // Printing the deque
    for (auto it = mydeque.begin(); it != mydeque.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
1 3 5 7 9
```

**clear() VS erase() . When to use what?**

**clear()** 从 deque 容器中移除所有元素，从而使其大小为 0。使用 clear()函数可以删除 deque 的所有元素。
**erase()** 功能另一方面，用于从容器中移除特定的元素或从容器中移除一系列元素，从而通过移除的元素数量来减小其大小。