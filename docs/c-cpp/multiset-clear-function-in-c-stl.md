# c++ STL 中的多集 clear()函数

> 原文:[https://www . geesforgeks . org/multist-clear-function-in-c-STL/](https://www.geeksforgeeks.org/multiset-clear-function-in-c-stl/)

**多集::clear()** 函数是 C++ STL 中的内置函数，它从多集容器中移除所有元素。移除后多集容器的最终大小为 0。

**语法:**

```cpp
multiset_name.clear()
```

**参数:**函数不接受任何参数。
**返回值:**函数不返回任何东西。

下面的程序说明了 multist::clear()函数:

**程序 1:**

## C++

```cpp
// C++ program to demonstrate the
// multiset::clear() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    int arr[] = { 15, 10, 15, 11, 10 };

    // initializes the set from an array
    multiset<int> s(arr, arr + 5);

    // prints all elements in set
    cout << "The elements in multiset are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    cout << "\nThe size after clear() is: ";

    // erases all elements
    s.clear();
    cout << s.size();

    return 0;
}
```

**Output:** 

```cpp
The elements in multiset are: 10 10 11 15 15 
The size after clear() is: 0
```

时间复杂度:O(N)，其中 N 是多集合中存在的元素总数。
辅助空间:O(N)

**程序 2:**

## C++

```cpp
// C++ program to demonstrate the
// multiset::clear() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    int arr[] = { 15, 10, 15, 11, 10, 18, 18, 20, 20 };

    // initializes the set from an array
    multiset<int> s(arr, arr + 9);

    // prints all elements in set
    cout << "The elements in multiset are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    cout << "\nThe size after clear() is: ";

    // erases all elements
    s.clear();
    cout << s.size();

    return 0;
}
```

**Output:** 

```cpp
The elements in multiset are: 10 10 11 15 15 18 18 20 20 
The size after clear() is: 0
```

时间复杂度:O(N)，其中 N 是多集合中存在的元素总数。
辅助空间:O(N)