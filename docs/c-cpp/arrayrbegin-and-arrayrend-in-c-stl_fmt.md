# C++ STL 中的 `array::rbegin()` 和 `array::rend()`

> 原文: [https://www.geeksforgeeks.org/arrayrbegin-and-arrayrend-in-c-stl/](https://www.geeksforgeeks.org/arrayrbegin-and-arrayrend-in-c-stl/)

## 1. `array::rbegin()`

`array::rbegin()` 是 C++ STL 中的一个内置函数，它返回一个反向迭代器，指向容器中的最后一个元素。

### 语法

```cpp
array_name.rbegin()
```

### 参数
该函数不接受任何参数。

### 返回值
该函数返回一个反向迭代器，指向容器中的最后一个元素。

### 演示 `array::rbegin()` 方法的程序

**程序 1:**

```cpp
// CPP program to illustrate
// the array::rbegin() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // array initialisation
    array<int, 5> arr = { 1, 5, 2, 4, 7 };

    // prints the last element
    cout << "The last element is " << *(arr.rbegin()) << endl;

    // prints all the elements
    cout << "The array elements in reverse order are:\n";
    for (auto it = arr.rbegin(); it != arr.rend(); it++)
        cout << *it << " ";

    return 0;
}
```

**输出:**

```cpp
The last element is 7
The array elements in reverse order are:
7 4 2 5 1
```

## 2. `array::rend()`

`array::rend()` 是 C++ STL 中的一个内置函数，它返回一个反向迭代器，指向数组容器中第一个元素之前的理论元素。

### 语法

```cpp
array_name.rend()
```

### 参数
该函数不接受任何参数。

### 返回值
该函数返回一个反向迭代器，指向数组容器中第一个元素之前的理论元素。

### 演示 `array::rend()` 方法的程序

**程序 1:**

```cpp
// CPP program to illustrate
// the array::rend() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    array<int, 5> arr = { 1, 5, 2, 4, 7 };

    // prints all the elements
    cout << "The array elements in reverse order are:\n";
    for (auto it = arr.rbegin(); it != arr.rend(); it++)
        cout << *it << " ";
    return 0;
}
```

**输出:**

```cpp
The array elements in reverse order are:
7 4 2 5 1
```