# 如何反向遍历 C++ 集合

> 原文:[https://www . geesforgeks . org/如何反向遍历 a-c-set/](https://www.geeksforgeeks.org/how-to-traverse-a-c-set-in-reverse-direction/)

给定一个[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)，任务是以相反的顺序遍历这个[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)。

**示例:**

```cpp
Input: set = [10 20 30 70 80 90 100 40 50 60]
Output: 100 90 80 70 60 50 40 30 20 10 

Input: set = [1 2 3 4 5]
Output: 5 4 3 2 1

```

**方法:**
要以相反的顺序遍历一个[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)，可以在其上声明一个 reverse_iterator，并且可以借助 [rbegin()和 rend()函数](https://www.geeksforgeeks.org/setrbegin-and-setrend-in-c-stl/)来遍历从最后一个元素到第一个元素的集合。

1.  去拿布景。
2.  在这个集合上声明反向迭代器。
3.  在 rbegin()和 rend()函数的帮助下，将集合从最后一个元素遍历到第一个元素。

下面是上述方法的实现:

**程序:**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Get the set
    int arr[] = { 14, 12, 15, 11, 10 };

    // initializes the set from an array
    set<int> s(arr, arr + sizeof(arr) / sizeof(arr[0]));

    // declare iterator on set
    set<int>::iterator it;

    cout << "Elements of Set in normal order:\n";

    // prints all elements in normal order
    // using begin() and end() methods
    for (it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    // declare reverse_iterator on set
    set<int>::reverse_iterator rit;

    cout << "\nElements of Set in reverse order:\n";

    // prints all elements in reverse order
    // using rbegin() and rend() methods
    for (rit = s.rbegin(); rit != s.rend(); rit++)
        cout << *rit << " ";

    return 0;
}
```

**Output:**

```cpp
Elements of Set in normal order:
10 11 12 14 15 
Elements of Set in reverse order:
15 14 12 11 10

```