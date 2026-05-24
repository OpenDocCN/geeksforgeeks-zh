# 使用 C++ STL 找到排序数组的下限和上限

> 原文:[https://www . geesforgeks . org/find-floor-and-ceil-of-sorted-array-use-STL/](https://www.geeksforgeeks.org/finding-floor-and-ceil-of-a-sorted-array-using-stl/)

给定一个排序的数组，任务是使用 STL 找到给定数字的[楼层和天花板](https://www.geeksforgeeks.org/ceil-floor-functions-cpp/)。
**例:**

```cpp
Input: arr[] = {1, 2, 4, 7, 11, 12, 23, 30, 32},
       values[] = { 1, 3, 5, 7, 20, 24 }
Output: Floor Values: 1 2 4 7 12 23 
       Ceil values: 1 4 7 7 23 30 
```

**如果是 floor()** : [下界()](https://www.geeksforgeeks.org/lower_bound-in-cpp/)将使用方法 os STL 来寻找下界。这将返回一个迭代器，指向范围[第一个，最后一个]中的第一个元素，该元素的比较结果不会小于目标。
**在 ceil()** 的情况下: [upper_bound()](https://www.geeksforgeeks.org/stdupper_bound-in-cpp/) 将使用方法 os STL 来查找上界。此方法返回一个迭代器，指向范围[第一个，最后一个]中比目标大的第一个元素。
**实施:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to find the floor and ceil
// of a given numbers in a sorted array

#include <bits/stdc++.h>
using namespace std;

// Function to find floor of list of
// values using lower_bound in STL
void printFloor(int arr[], int n1,
                int findFloor[], int n2)
{
    // Find and print the Floor Values
    int low;

    cout << "Floor : ";
    for (int i = 0; i < n2; i++) {

        low = (lower_bound(arr, arr + n1,
                           findFloor[i])
               - arr);

        if (arr[low] > findFloor[i])
            cout << arr[low - 1] << " ";
        else
            cout << arr[low] << " ";
    }

    cout << endl;
}
ceil
// Function to find Ceil of list of
// values using upper_bound in STL
void printCeil(int arr[], int n1,
               int findCeil[], int n2)
{
    // Find and print the Ceil Values
    int up;
    cout << "Ceil : ";
    for (int i = 0; i < n2; i++) {

        up = (upper_bound(arr, arr + n1,
                          findCeil[i])
              - arr);

        if (arr[up] > findCeil[i]
            && arr[up - 1] == findCeil[i]) {
            cout << arr[up - 1] << " ";
        }
        else
            cout << arr[up] << " ";
    }
    cout << endl;
}

// Driver code
int main()
{
    // Get the sorted array
    int arr[] = { 1, 2, 4, 7, 11, 12, 23, 30, 32 };
    int n1 = sizeof(arr) / sizeof(arr[0]);

    // Print Array
    cout << "Original Array: ";
    for (unsigned int i = 0; i < n1; i++)
        cout << " " << arr[i];
    cout << "\n";

    // Given values whose floor and ceil
    // values are needed to find
    int find[] = { 1, 3, 5, 7, 20, 24 };
    int n2 = sizeof(find) / sizeof(find[0]);

    // Print Values whose floor
    // and ceil is to be found
    cout << "Values: ";
    for (unsigned int i = 0; i < n2; i++)
        cout << find[i] << " ";
    cout << "\n";

    // Print Floor Values
    printFloor(arr, n1, find, n2);

    // Print Ceil Values
    printCeil(arr, n1, find, n2);

    return 0;
}
```

**Output:** 

```cpp
Array:  1 2 4 7 11 12 23 30 32
Values: 1 3 5 7 20 24 
Floor : 1 2 4 7 12 23 
Ceil  : 1 4 7 7 23 30
```