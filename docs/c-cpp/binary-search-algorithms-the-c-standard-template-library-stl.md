# c++ 标准模板库(STL)中的二分搜索法

> 原文:[https://www . geesforgeks . org/binary-search-algorithms-the-c-standard-template-library-STL/](https://www.geeksforgeeks.org/binary-search-algorithms-the-c-standard-template-library-stl/)

[二分搜索法](https://www.geeksforgeeks.org/binary-search/)是一种广泛使用的搜索算法，它要求在应用搜索之前对数组进行排序。这个算法背后的主要思想是不断地将数组分成两半(分治)，直到找到元素，或者所有的元素都用完。
它的工作原理是将数组的中间项与我们的目标进行比较，如果匹配，则返回 true，否则如果中间项大于目标，则在左边的子数组中执行搜索。
如果中间项小于目标，则在右子阵列中执行搜索。

二分搜索法的原型是:

```cpp
binary_search(startaddress, 
              endaddress, valuetofind)
Parameters :
startaddress: the address of the first 
              element of the array.
endaddress: the address of the next contiguous 
            location of the last element of the array.
valuetofind: the target value which we have 
             to search for.
Returns :
true if an element equal to valuetofind is found, else false.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to implement
// Binary Search in
// Standard Template Library (STL)
#include <algorithm>
#include <iostream>

using namespace std;

void show(int a[], int arraysize)
{
    for (int i = 0; i < arraysize; ++ i)
        cout << a[i] << ",";
}

int main()
{
    int a[] = { 1, 5, 8, 9, 6, 7, 3, 4, 2, 0 };
    int asize = sizeof(a) / sizeof(a[0]);
    cout << "\nThe array is : \n";
    show(a, asize);

    cout << "\n\nLet's say we want to search for ";
    cout << "\n2 in the array So, we first sort the array";
    sort(a, a + asize);
    cout << "\n\nThe array after sorting is : \n";
    show(a, asize);
    cout << "\n\nNow, we do the binary search";
    if (binary_search(a, a + 10, 2))
        cout << "\nElement found in the array";
    else
        cout << "\nElement not found in the array";

    cout << "\n\nNow, say we want to search for 10";
    if (binary_search(a, a + 10, 10))
        cout << "\nElement found in the array";
    else
        cout << "\nElement not found in the array";

    return 0;
}
```

**Output**

```cpp
The array is : 
1,5,8,9,6,7,3,4,2,0,

Let's say we want to search for 
2 in the array So, we first sort the array

The array after sorting is : 
0,1,2,3,4,5,6,7,8,9,

Now, we do the binary search
Element found in the array

Now, say we want to search for 10
Element not found in the array
```

**相关文章:**[STD::b 在 C++ 中搜索](https://www.geeksforgeeks.org/stdbsearch-in-cpp/)
如果发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论