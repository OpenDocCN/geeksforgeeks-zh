# 在 C++ STL 中列出 cbegin()和 cend()函数

> 原文:[https://www . geesforgeks . org/list-CBE gin-and-cend-function-in-c-STL/](https://www.geeksforgeeks.org/list-cbegin-and-cend-function-in-c-stl/)

*   **列表::cbegin()** 是 C++ STL 中的内置函数，它返回一个指向列表开头的常量随机访问迭代器。因此，获得的迭代器可以用于迭代容器，但不能用于修改它所指向的对象的内容，即使对象本身不是常数。
    **语法:**

```cpp
list_name.cbegin()
```

**参数:**函数不接受任何参数。
**返回值:**返回一个指向列表开头的常量随机访问迭代器。
以下程序说明了上述功能:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// cbegin() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // declaration of list
    list<int> lis = { 5, 6, 7, 8, 9 };

    // Prints the first element
    cout << "The first element is: " << *lis.cbegin();

    // printing list elements
    cout << "\nList: ";

    for (auto it = lis.cbegin(); it != lis.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:** 

```cpp
The first element is: 5
List: 5 6 7 8 9
```

*   **列表::cend()** 是 C++ STL 中的一个内置函数，它返回一个指向列表末尾的常量随机访问迭代器。因此，获得的迭代器可以用于迭代容器，但不能用于修改它所指向的对象的内容，即使对象本身不是常数。
    **语法:**

```cpp
list_name.cend()
```

**参数:**函数不接受任何参数。
**返回值:**返回一个指向列表末尾的常量随机访问迭代器。
下面程序说明了功能:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// cend() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration of list
    list<int> lis = { 10, 20, 30, 40, 50 };

    // printing list elements
    cout << "List: " << endl;

    for (auto it = lis.cbegin(); it != lis.cend(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:** 

```cpp
List: 
10 20 30 40 50
```