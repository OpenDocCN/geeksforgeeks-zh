# c++ STL 中的无序 _ 集合交换()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-swap-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-swap-function-in-c-stl/)

**无序集::swap()** 方法是 C++ STL 中的一个内置函数，用于交换两个无序集容器的值。它交换两个无序集容器的元素。大小可能不同，但它会交换元素并改变元素的顺序。

**语法**:

```cpp
unordered_set_firstname.swap(unordered_set_secondname)

```

**参数**:该函数接受一个强制参数**第二个 _ 名称**，该参数指定了要与第一个参数交换的第二个无序 _ 集合。

**返回值**:这个函数不返回任何东西。

下面的程序说明了*无序 _ 集合::交换()*功能:

```cpp
// C++ program to illustrate the
// unordered_set_swap() function
#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_set<int> arr1 = { 1, 2, 3, 4, 5 };
    unordered_set<int> arr2 = { 5, 6, 7, 8, 9 };

    cout << "The elements of arr1 before swap(): ";

    for (auto it = arr1.begin(); it != arr1.end(); it++) {
        cout << *it << " ";
    }

    cout << "\nThe elements of arr2 before swap(): ";
    for (auto it = arr2.begin(); it != arr2.end(); it++) {
        cout << *it << " ";
    }

    // inbuilt swap function to swap
    // elements of two unordered_set
    swap(arr1, arr2);

    cout << "\n\nThe elements of arr1 after swap(): ";
    // elemen
    for (auto it = arr1.begin(); it != arr1.end(); it++) {
        cout << *it << " ";
    }

    cout << "\nThe elements of arr2 after swap(): ";
    for (auto it = arr2.begin(); it != arr2.end(); it++) {
        cout << *it << " ";
    }

    return 0;
}
```

**Output:**

```cpp
The elements of arr1 before swap(): 5 1 2 3 4 
The elements of arr2 before swap(): 9 5 6 7 8 

The elements of arr1 after swap(): 9 5 6 7 8 
The elements of arr2 after swap(): 5 1 2 3 4

```