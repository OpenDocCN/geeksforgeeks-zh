# 检查一个数组中的所有元素是否在 C++ 中使用库

> 原文:[https://www . geesforgeks . org/check-数组中的所有元素都是偶数-使用 cpp 中的库/](https://www.geeksforgeeks.org/check-all-the-elements-in-an-array-are-even-using-library-in-cpp/)

给我们一个元素数组，我们必须检查每个元素是否为偶数。

示例:

```cpp
Input : [2, 4, 6, 8, 9]
Output : All the elements are not even

Input : [4, 6, 8, 12, 14]
Output : Alla the elements are even

```

**方法:**使用 for 循环可以解决上述问题，但是在 C++ 中，我们有 [**all_of()**](https://www.geeksforgeeks.org/useful-array-algorithms-in-c-stl/) 算法，该算法对整个数组进行操作，节省了编写循环代码和检查每个元素的指定属性的时间。

注意 [**all_of()**](https://www.geeksforgeeks.org/useful-array-algorithms-in-c-stl/) 内部也使用循环，只是节省了我们写循环代码的时间。

```cpp
// CPP program to check if all elements
// of an array are even or odd.
#include <algorithm>
#include <iostream>
using namespace std;

void even_or_not(int arr[], int len)
{
    // all_of() returns true if given operation is true
    // for all elements, otherwise returns false.
    all_of(arr, arr + len, [](int i) { return i % 2; }) ? 
                        cout << "All are even elements" : 
                        cout << "All are not even elements";
}

int main()
{
    int arr[] = { 2, 4, 6, 12, 14, 17 };
    int len = sizeof(arr) / sizeof(arr[0]);
    even_or_not(arr, len);
    return 0;
}
```

输出:

```cpp
All are not even elements

```