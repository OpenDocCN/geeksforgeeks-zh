# c++ STL 中的数组数据()，示例

> 原文:[https://www . geesforgeks . org/array-data-in-c-STL-with-examples/](https://www.geeksforgeeks.org/array-data-in-c-stl-with-examples/)

**数组::data()** 是 C++ STL 中的内置函数，返回指向数组对象中第一个元素的指针。

**语法:**

```cpp
array_name.data()
```

**参数:**函数不接受任何参数。

**返回值:**函数返回一个指针。

以下程序说明了上述功能:

**程序 1:**

```cpp
// CPP program to demonstrate the
// array::data() function
#include <bits/stdc++.h>
using namespace std;
int main()
{
    array<int, 5> arr = { 1, 2, 3, 4, 5 };

    // prints the array elements
    cout << "The array elements are: ";
    for (auto it = arr.begin(); it != arr.end(); it++)
        cout << *it << " ";

    // Points to the first element
    auto it = arr.data();

    cout << "\nThe first element is:" << *it;

    return 0;
}
```

**Output:**

```cpp
The array elements are: 1 2 3 4 5 
The first element is:1

```

**程序 2:**

```cpp
// CPP program to demonstrate the
// array::data() function
#include <bits/stdc++.h>
using namespace std;
int main()
{
    array<int, 5> arr = { 1, 2, 3, 4, 5 };

    // prints the array elements
    cout << "The array elements are: ";
    for (auto it = arr.begin(); it != arr.end(); it++)
        cout << *it << " ";

    // Points to the first element
    auto it = arr.data();

    // increment
    it++ ;
    cout << "\nThe second element is: " << *it;

    // increment
    it++ ;
    cout << "\nThe third element is: " << *it;

    return 0;
}
```

**Output:**

```cpp
The array elements are: 1 2 3 4 5 
The second element is: 2
The third element is: 3

```