# c++ 中的矢量擦除()和清除()

> 原文:[https://www . geesforgeks . org/vector-erase-and-clear-in-CPP/](https://www.geeksforgeeks.org/vector-erase-and-clear-in-cpp/)

[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)与动态数组相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。

**vector::clear()**

clear()函数用于移除向量容器的所有元素，从而使其大小为 0。
**语法:**

```cpp
***vectorname***.clear()
Parameters :
No parameters are passed.
Result :
All the elements of the vector are
removed ( or destroyed )
```

**示例:**

```cpp
Input  : myvector= {1, 2, 3, 4, 5};
         myvector.clear();
Output : myvector= {}

Input  : myvector= {};
         myvector.clear();
Output : myvector= {}
```

**错误和异常**
1。它有一个无异常抛出保证。
2。传递参数时显示错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of clear() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector;
    myvector.push_back(1);
    myvector.push_back(2);
    myvector.push_back(3);
    myvector.push_back(4);
    myvector.push_back(5);

    // Vector becomes 1, 2, 3, 4, 5

    myvector.clear();
    // vector becomes empty

    // Printing the vector
    for (auto it = myvector.begin(); it != myvector.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
*No Output*
```

**时间复杂度:** O(N)
所有元素都被一一摧毁。

**vector::erase()**

erase()函数用于从指定位置或范围移除容器中的元素。
**语法:**

```cpp
1\. ***vectorname***.erase(***position***)
2\. ***vectorname***.erase(***startingposition***, ***endingposition***)
Parameters :
Position of the element to be removed in the form of iterator.
or the range specified using start and end iterator.
Result :
Elements are removed from the specified
position of the container.
```

示例:

```cpp
Input  : myvector= {1, 2, 3, 4, 5}, iterator= myvector.begin()+2
         myvector.erase(iterator);
Output : 1, 2, 4, 5

Input  : myvector= {1, 2, 3, 4, 5, 6, 7, 8}, iterator1= myvector.begin()+3, iterator2= myvector.begin()+6
         myvector.erase(iterator1, iterator2);
Output : 1, 2, 3, 7, 8
```

**错误和异常**
1。如果该位置有效，它有一个无异常抛出保证。
2。否则显示未定义的行为。
**从** a **特定位置移除**a**元素:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// working of erase() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector{ 1, 2, 3, 4, 5 };
    vector<int>::iterator it;

    it = myvector.begin();
    myvector.erase(it);

    // Printing the Vector
    for (auto it = myvector.begin(); it != myvector.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
2 3 4 5
```

**移除范围内的元素:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of erase() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector{ 1, 2, 3, 4, 5 };
    vector<int>::iterator it1, it2;

    it1 = myvector.begin();
    it2 = myvector.end();
    it2--;
    it2--;

    myvector.erase(it1, it2);

    // Printing the Vector
    for (auto it = myvector.begin(); it != myvector.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
4 5
```

**应用程序**
给定一个整数列表，从向量中移除所有偶数元素并打印向量。

```cpp
Input  :1, 2, 3, 4, 5, 6, 7, 8, 9
Output :1 3 5 7 9
*Explanation - 2, 4, 6 and 8 which are even are erased from the vector*
```

**算法**
1。运行一个循环，直到向量的大小。
2。检查每个位置的元素是否可以被 2 整除，如果可以，移除元素并递减迭代器。
3。打印最终矢量。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Application of erase() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector{ 1, 2, 3, 4, 5, 6, 7, 8, 9 };

    for (auto i = myvector.begin(); i != myvector.end(); ++ i) {
        if (*i % 2 == 0) {
            myvector.erase(i);
            i--;
        }
    }

    // Printing the vector
    for (auto it = myvector.begin(); it != myvector.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
1 3 5 7 9
```

**时间复杂度:** O(N <sup>2</sup> )在最差的情况下作为擦除需要线性时间。

**clear() vs erase(), When to use what?**

**clear()** 从向量容器中移除所有元素，从而使其大小为 0。使用 clear()函数移除向量的所有元素。
**erase()** 功能则相反，用于从容器中移除特定元素或从容器中移除一系列元素，从而通过移除的元素数量来减小其大小。