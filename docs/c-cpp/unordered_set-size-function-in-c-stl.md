# c++ STL 中的无序 _ 集大小()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-size-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-size-function-in-c-stl/)

**无序集::size()** 方法是 C++ STL 中的一个内置函数，用于返回无序集容器中的元素数量。

**语法**:

```cpp
*unordered_set_name*.size()
```

**参数**:不接受任何参数。

**返回值**:该函数返回容器中元素的个数。

以下程序说明了*无序 _ 集合::大小()*功能:

**程序 1:**

```cpp
// C++ program to illustrate the 
// unordered_set.size() function 
#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_set<int> arr1 = { 1, 2, 3, 4, 5 };

    // prints the size of arr1
    cout << "size of arr1:" << arr1.size();

    // prints the element
    cout << "\nThe elements are: ";
    for (auto it = arr1.begin(); it != arr1.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
size of arr1:5
The elements are: 5 1 2 3 4

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_set::size() function
// when container is empty
#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_set<int> arr2 = {};

    // prints the size
    cout << "Size of arr2 : " << arr2.size();

    return 0;
}
```

**Output:**

```cpp
Size of arr2 : 0

```