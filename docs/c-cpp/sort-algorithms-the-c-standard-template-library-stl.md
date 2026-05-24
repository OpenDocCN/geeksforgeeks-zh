# 在 C++ 标准模板库中排序(STL)

> 原文:[https://www . geesforgeks . org/sort-algorithms-the-c-standard-template-library-STL/](https://www.geeksforgeeks.org/sort-algorithms-the-c-standard-template-library-stl/)

[排序](https://www.geeksforgeeks.org/sorting-algorithms/)是应用于数据的最基本功能之一。这意味着以特定的方式排列数据，可以是增加的，也可以是减少的。C++ STL 中有一个名为 sort()的内置函数。
这个函数内部使用了 IntroSort。更详细地说，它是使用快速排序、堆排序和插入排序的混合来实现的。默认情况下，它使用快速排序，但是如果快速排序进行了不公平的分区，并且花费了 N*logN 以上的时间，它会切换到 HeapSort，当数组变得非常小时，它会切换到 InsertionSort。

排序的原型是:

```cpp
sort(startaddress, endaddress)

startaddress: the address of the first 
              element of the array
endaddress: the address of the next 
            contiguous location of the 
            last element of the array.
So actually sort() sorts in the 
range of [startaddress,endaddress)
```

## C++

```cpp
// C++ program to sort an array
#include <algorithm>
#include <iostream>

using namespace std;

void show(int a[], int array_size)
{
    for (int i = 0; i < array_size; ++ i)
        cout << a[i] << " ";
}

// Driver code
int main()
{
    int a[] = { 1, 5, 8, 9, 6, 7, 3, 4, 2, 0 };

    // size of the array
    int asize = sizeof(a) / sizeof(a[0]);
    cout << "The array before sorting is : \n";

    // print the array
    show(a, asize);

      // sort the array
    sort(a, a + asize);

    cout << "\n\nThe array after sorting is :\n";

    // print the array after sorting
    show(a, asize);

    return 0;
}
```

**Output**

```cpp
The array before sorting is : 
1 5 8 9 6 7 3 4 2 0 

The array after sorting is :
0 1 2 3 4 5 6 7 8 9 
```

详见 [std::sort()](https://www.geeksforgeeks.org/sort-c-stl/) 。