# c++ STL 中的无序 _ 映射交换

> 原文:[https://www.geeksforgeeks.org/unordered_map-swap-in-c-stl/](https://www.geeksforgeeks.org/unordered_map-swap-in-c-stl/)

**STD::unordered _ map::swap()**是 C++ STL 中的内置函数，它将一个容器的元素交换到另一个容器。调用此函数后，调用方无序映射的元素将是被调用方无序映射的元素，而被调用方无序映射的元素将是调用方无序映射的元素。
元素的内部交换没有完成，只有两个无序映射的引用类型被改变。
**语法**

```cpp
unordered_map.swap ( unordered_map& ump )

```

**返回类型:**该功能的返回类型为空。
**参数:**另一张元素类型相同的无序 _ 地图。
**复杂度:**其复杂度不变。

**例 1**

```cpp
// C++ code to illustrate the method
// unordered_map swap
#include <bits/stdc++.h>

using namespace std;

int main()
{
    unordered_map<int, int> sample1, sample2;

    // Map initialization
    sample1 = { { 2, 2 }, { 3, 4 }, { 4, 6 }, { 5, 8 } };
    sample2 = { { 10, 11 }, { 12, 13 }, { 14, 15 }, { 26, 17 } };

    // printing details before calling swap

    cout << " Elements of maps before swap \n";
    cout << " Elements of first map are : \n";
    for (auto& x : sample1)
        cout << x.first << " : " << x.second << endl;

    cout << " Elements of second map are : \n";
    for (auto& x : sample2)
        cout << x.first << " : " << x.second << endl;

    // swapping
    sample1.swap(sample2);

    cout << " Elements of maps after swap \n";
    cout << " Elements of first map are : \n";
    for (auto& x : sample1)
        cout << x.first << " : " << x.second << endl;

    cout << " Elements of second map are : \n";
    for (auto& x : sample2)
        cout << x.first << " : " << x.second << endl;
    return 0;
}
```

**Output:**

```cpp
Elements of maps before swap 
 Elements of first map are : 
5 : 8
4 : 6
3 : 4
2 : 2
 Elements of second map are : 
14 : 15
26 : 17
12 : 13
10 : 11
 Elements of maps after swap 
 Elements of first map are : 
14 : 15
26 : 17
12 : 13
10 : 11
 Elements of second map are : 
5 : 8
4 : 6
3 : 4
2 : 2

```