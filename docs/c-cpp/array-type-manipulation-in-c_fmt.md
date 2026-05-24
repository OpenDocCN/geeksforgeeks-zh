# C++ 中的数组类型操作

> 原文: [https://www.geeksforgeeks.org/array-type-manipulation-in-c/](https://www.geeksforgeeks.org/array-type-manipulation-in-c/)

本文演示了一些可以用来查询和操作数组类型的内置函数，甚至是多维数组。这些函数在我们需要信息或操作不同维度的数组时非常有用。这些函数在 `<type_traits>` 头文件中定义。一些函数包括:

## 1. `is_array()`
顾名思义，这个函数的唯一目的是检查一个变量是否是数组类型。值得注意的是，根据这个函数，即使是 `std::array` 也不被视为数组。成员常量 `value` 在类型是数组时返回 `true`，否则返回 `false`。

## 2. `is_same()`
此功能是检查**类型关系**，如果两个类型具有完全相同的特征，则返回 `true`。如果类型相同，成员常量 `value` 返回 `true`，否则返回 `false`。

```cpp
// C++ code to demonstrate the working of 
// is_array() and is_same()

#include<type_traits>
#include<iostream>
#include<array>
#include<string>
using namespace std;

int main()
{
    // checking which is array using is_array
    cout << "Is Integer an array? : " << is_array<int>::value << endl;

    cout << "Is Array an array? : " << is_array<int[10]>::value << endl;

    cout << "Is 2D Array an array? : " 
         << is_array<int[10][10]>::value << endl;

    cout << "Is String an array? : " << is_array<string>::value << endl;

    cout << "Is Character Array an array? : " 
         << is_array<char[10]>::value << endl;

    cout << "Is Array class type an array? : " 
         << is_array<array<int,3>>::value << endl;

    cout << endl;

    // checking for same types using is_same()
    cout << "Is 2D array same as 1D array? : " << 
       is_same<int[10],int[10][10]>::value << endl;

    cout << "Is Character array same as Integer array? : " 
         << is_same<int[10],char[10]>::value << endl;

    cout << "Is 1D array same as 1D array (Different sizes) ? : " 
         << is_same<int[10],int[20]>::value << endl;

    cout << "Is 1D array same as 1D array? (Same sizes): " 
         << is_same<int[10],int[10]>::value << endl;
    return 0;
}
```

输出:

```
Is Integer an array? : 0
Is Array an array? : 1
Is 2D Array an array? : 1
Is String an array? : 0
Is Character Array an array? : 1
Is Array class type an array? : 0

Is 2D array same as 1D array? : 0
Is Character array same as Integer array? : 0
Is 1D array same as 1D array (Different sizes) ? : 0
Is 1D array same as 1D array? (Same sizes): 1
```

## 3. `rank()`
这是一个**属性查询函数**，它返回数组的秩（rank），即数组的维度。成员常量 `value` 返回对象的秩。

```cpp
// C++ code to demonstrate the working of 
// rank()

#include<type_traits> // for array query functions
#include<iostream>
using namespace std;

int main()
{
    // checking rank of different types
    cout << "The rank of integer is : " << rank<int>::value << endl;

    cout << "The rank of 1D integer array is : " 
         << rank<int[10]>::value << endl;

    cout << "The rank of 2D integer array is : " 
         << rank<int[20][10]>::value << endl;

    cout << "The rank of 3D integer array is : " 
         << rank<int[20][10][40]>::value << endl;

    cout << "The rank of 1D character array is : " 
         << rank<char[10]>::value << endl;

    cout << endl;
}
```

输出:

```
The rank of integer is : 0
The rank of 1D integer array is : 1
The rank of 2D integer array is : 2
The rank of 3D integer array is : 3
The rank of 1D character array is : 1
```

## 4. `extent()`
`extent` 和 `remove_extent` 都是**复合类型变化**，可以应用于 C++ 中的数组。此函数返回数组特定维度的大小。此函数有两个参数：数组类型和维度索引（从0开始）。它也有成员常量 `value` 用于打印值。

## 5. `remove_extent()`
此函数从声明的矩阵/数组中删除最左边的第一个维度。

## 6. `remove_all_extents()`
此函数移除矩阵/数组的所有维度，并将其转换为基本数据类型。

```cpp
// C++ code to demonstrate the working of 
// extent(), remove_extent() and remove_all_extents()

#include<type_traits> // for array query functions
#include<iostream>
using namespace std;

int main()
{
    // checking extent of different dimensions
    cout << "The extent of 1st dimension of 3D integer array is  : " 
         << extent<int[20][10][40], 0>::value << endl;

    cout << "The extent of 2nd dimension of 3D integer array is  : " 
         << extent<int[20][10][40], 1>::value << endl;

    cout << "The extent of 3rd dimension of 3D integer array is  : " 
         << extent<int[20][10][40], 2>::value << endl;

    cout << "The extent of 4th dimension of 3D integer array is  : " 
         << extent<int[20][10][40], 3>::value << endl;

    cout << endl;

    // checking remove_extent
    cout << "The rank after removing 1 extent is : " 
         << rank<remove_extent<int[20][10][40]>::type>::value << endl;

    cout << "The extent of 1st after removing 1 extent is : " 
         << extent<remove_extent<int[20][10][40]>::type>::value << endl;

    cout << endl;

    // checking remove_all_extents
    cout << "The rank after removing all extents is : " 
         << rank<remove_all_extents<int[20][10][40]>::type>::value << endl;

    cout << "The extent of 1st after removing all extents is : " 
         << extent<remove_all_extents<int[20][10][40]>::type>::value << endl;
}
```

输出:

```
The extent of 1st dimension of 3D integer array is  : 20
The extent of 2nd dimension of 3D integer array is  : 10
The extent of 3rd dimension of 3D integer array is  : 40
The extent of 4th dimension of 3D integer array is  : 0

The rank after removing 1 extent is : 2
The extent of 1st after removing 1 extent is : 10

The rank after removing all extents is : 0
The extent of 1st after removing all extents is : 0
```

如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论。