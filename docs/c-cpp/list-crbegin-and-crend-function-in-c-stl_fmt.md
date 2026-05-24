# 在 C++ STL 中列出 `crbegin()` 和 `crend()` 函数

> 原文：[https://www.geeksforgeeks.org/list-crbegin-and-crend-function-in-c-stl/](https://www.geeksforgeeks.org/list-crbegin-and-crend-function-in-c-stl/)

## 1. `list::crbegin()`
`list::crbegin()` 是 C++ STL 中的一个内置函数，它返回一个常量反向迭代器，指向列表的最后一个元素，即容器的反向开头。由于迭代器是常量的，因此无法修改或更改元素。

### 语法
```cpp
list_name.crbegin()
```

### 参数
函数不接受任何参数。

### 返回值
返回一个随机访问反向迭代器，指向列表的反向开头。

下面的程序说明了上面的功能：
```cpp
// C++ program to illustrate the
// list::crbegin() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // declaration of the list
    list<int> lis = { 10, 20, 30, 40, 50 };

    // prints the last element
    cout << "The last element is: " << *lis.crbegin();
    cout << "\nList: ";

    for (auto it = lis.crbegin(); it != lis.crend(); ++ it)
        cout << *it << " ";

    return 0;
}
```

### 输出
```cpp
The last element is: 50
List: 50 40 30 20 10
```

## 2. `list::crend()`
`list::crend()` 是 C++ STL 中的一个内置函数，它返回一个常量反向迭代器，指向列表中第一个元素之前的理论元素，即列表的反向结尾。由于迭代器是常量的，因此无法修改或更改元素。

### 语法
```cpp
list_name.crend()
```

### 参数
函数不接受任何参数。

### 返回值
返回一个常量随机反向迭代器，指向列表的反向结尾。

下面的程序说明了上面的功能：
```cpp
// C++ program to illustrate the
// list::crend() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // declaration of the list
    list<int> lis = { 7, 6, 5, 4, 3, 2 };

    cout << "List: " << endl;

    for (auto it = lis.crbegin(); it != lis.crend(); ++ it)
        cout << *it << " ";

    return 0;
}
```

### 输出
```cpp
List: 
2 3 4 5 6 7
```