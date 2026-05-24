# c++ STL 中的 forward _ list::swap()

> 原文:[https://www.geeksforgeeks.org/forward_listswap-in-c-stl/](https://www.geeksforgeeks.org/forward_listswap-in-c-stl/)

**forward_list::swap()** 是 CPP STL 中的内置函数，它将第一个给定 forward_list 的内容与另一个 forward_list 进行交换。

**语法:**

```cpp
swap(forward_list first, forward_list second)
               or 
forward_list1.swap(forward_list second)

```

**参数:**该函数接受两个参数，如下所示:

*   *第一个*–第一个转发列表
*   *第二个*–第二个转发列表

**返回值:**函数不返回任何内容。它交换两个列表。

以下程序演示了上述功能:

**程序 1:**

```cpp
// CPP program that demonstrates the
// forward_list::swap() function
// when two parameters is passed
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialising the two forward_list
    forward_list<int> firstlist = { 9, 8, 7, 6 };

    forward_list<int> secondlist = { 10, 20, 30 };

    // printing elements before the swap operation
    // for firstlist and secondlist
    cout << "Before swap operation firstlist was: ";
    for (auto it = firstlist.begin(); it != firstlist.end(); ++ it)
        cout << *it << " ";

    cout << "\nBefore swap operation secondlist was: ";
    for (auto it = secondlist.begin(); it != secondlist.end(); ++ it)
        cout << *it << " ";

    // swap operation on two lists
    swap(firstlist, secondlist);

    // printing elements after the swap operation
    // for forward1 and secondlist
    cout << "\n\nAfter swap operation firstlist is: ";

    for (auto it = firstlist.begin(); it != firstlist.end(); ++ it)
        cout << *it << " ";
    cout << "\nAfter swap operation secondlist is:";
    for (auto it = secondlist.begin(); it != secondlist.end(); ++ it)
        cout << *it << " ";
    return 0;
}
```

**Output:**

```cpp
Before swap operation firstlist was: 9 8 7 6 
Before swap operation secondlist was: 10 20 30 

After swap operation firstlist is: 10 20 30 
After swap operation secondlist is:9 8 7 6

```

**程序 2:**

```cpp
// CPP program that demonstrates the
// forward_list::swap() function
// when two parameters is passed
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialising the two forward_list
    forward_list<int> firstlist = { 9, 8, 7, 6 };

    forward_list<int> secondlist = { 10, 20, 30 };

    // printing elements before the swap operation
    // for firstlist and secondlist
    cout << "Before swap operation firstlist was: ";
    for (auto it = firstlist.begin(); it != firstlist.end(); ++ it)
        cout << *it << " ";

    cout << "\nBefore swap operation secondlist was: ";
    for (auto it = secondlist.begin(); it != secondlist.end(); ++ it)
        cout << *it << " ";

    // swap operation on two lists
    firstlist.swap(secondlist);

    // printing elements after the swap operation
    // for forward1 and secondlist
    cout << "\n\nAfter swap operation firstlist is: ";

    for (auto it = firstlist.begin(); it != firstlist.end(); ++ it)
        cout << *it << " ";
    cout << "\nAfter swap operation secondlist is:";
    for (auto it = secondlist.begin(); it != secondlist.end(); ++ it)
        cout << *it << " ";
    return 0;
}
```

**Output:**

```cpp
Before swap operation firstlist was: 9 8 7 6 
Before swap operation secondlist was: 10 20 30 

After swap operation firstlist is: 10 20 30 
After swap operation secondlist is:9 8 7 6

```