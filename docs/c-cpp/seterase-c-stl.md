# 设置::在 C++ STL 中擦除

> 原文:[https://www.geeksforgeeks.org/seterase-c-stl/](https://www.geeksforgeeks.org/seterase-c-stl/)

[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)是一种关联容器，其中每个元素必须是唯一的，因为元素的值标识了它。元素的值一旦添加到集合中就不能修改，尽管可以移除和添加该元素的修改值。

**set::erase()**

erase()函数用于从指定位置或范围移除容器中的元素。
**语法:**

```cpp
1\. ***setname.erase(position)***
2\. ***setname.erase(startingposition, endingposition)***
Parameters :
Position of the element to be removed in 
the form of iterator or the range specified
using start and end iterator.
Result :
Elements are removed from the specified
position of the container.
```

示例:

```cpp
Input  : myset{1, 2, 3, 4, 5}, iterator= 2
         myset.erase(iterator);
Output : 1, 2, 4, 5

Input  : myset{1, 2, 3, 4, 5, 6, 7, 8}, 
         iterator1= 3, iterator2= 6
         myset.erase(iterator1, iterator2);
Output : 1, 2, 3, 8
```

**错误和异常**
1。如果位置有效，它有一个无异常抛出保证。
2。否则显示未定义的行为。
**从特定位置移除元素**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// INTEGER SET EXAMPLE
// CPP program to illustrate
// Implementation of erase() function
#include <iostream>
#include <set>

using namespace std;

int main()
{
    // set declaration
    set<int> myset{ 1, 2, 3, 4, 5 };
    set<int>::iterator it1, it2;

    // defining it1 pointing to the first
    // element and it2 to the last element
    it1 = myset.begin();
    it2 = myset.end();

    // decrementing the it2 two times
    it2--;
    it2--;

    // erasing elements within the range
    // of it1 and it2
    myset.erase(it1, it2);

    // Printing the set
    for (auto it = myset.begin();
        it != myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
4 5
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CHARACTER SET EXAMPLE
// CPP program to illustrate
// Implementation of erase() function
#include <iostream>
#include <set>

using namespace std;

int main()
{
    // set declaration
    set<char> myset{ 'A', 'C', 'E', 'G' };
    set<char>::iterator it1, it2;

    // defining it1 pointing to the first
    // element and it2 to the last element
    it1 = myset.begin();
    it2 = myset.end();

    // decrementing the it2 two times
    it2--;
    it2--;

    // erasing elements within the
    // range of it1 and it2
    myset.erase(it1, it2);

    // Printing the set
    for (auto it = myset.begin();
        it != myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
E G
```

**移除范围内的元素**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// INTEGER SET EXAMPLE
// CPP program to illustrate
// Implementation of erase() function
#include <iostream>
#include <set>

using namespace std;

int main()
{
    // set declaration
    set<int> myset{ 1, 2, 3, 4, 5 };
    set<int>::iterator it;

    // defining iterator pointing
    // to the first element
    it = myset.begin();

    // erasing the first element
    myset.erase(it);

    // Printing the set
    for (auto it = myset.begin();
        it != myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
2 3 4 5
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CHARACTER SET EXAMPLE
// CPP program to illustrate
// Implementation of erase() function
#include <iostream>
#include <set>

using namespace std;

int main()
{
    // set declaration
    set<char> myset{ 'A', 'B', 'C', 'D' };
    set<char>::iterator it;

    // defining iterator pointing
    // to the first element
    it = myset.begin();

    // erasing the first element
    myset.erase(it);

    // Printing the set
    for (auto it = myset.begin();
        it != myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
B C D
```

**时间复杂度:**
1。*设定名称*。擦除(*位置*)–摊销常数
2。*设定名称*。擦除(*起始位置，结束位置*)–O(n)，n 是起始位置和结束位置之间的元素数量。
**应用程序**
给定一组整数，从集合中移除所有偶数元素并打印集合。

```cpp
Input  :1, 2, 3, 4, 5, 6, 7, 8, 9
Output :1 3 5 7 9
Explanation - 2, 4, 6 and 8 which are even are erased from the set
```

**算法**
1。运行一个循环，直到集合的大小。
2。检查每个位置的元素是否可以被 2 整除，如果可以，移除元素并将返回迭代器分配给当前迭代器，如果不可以，递增迭代器。
3。打印最后一套。
注意:擦除返回下一个元素的迭代器

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Application of erase() function
#include <iostream>
#include <set>

using namespace std;

int main()
{
    // set declaration
    set<int> myset{ 1, 2, 3, 4, 5, 6, 7, 8, 9 };

    // checking for even elements and removing them
    for (auto i = myset.begin(); i != myset.end(); ) {
        if (*i % 2 == 0)
            i=myset.erase(i);
        else
            i++ ;

    }

    // Printing the set
    for (auto it = myset.begin(); it != myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
1 3 5 7 9
```