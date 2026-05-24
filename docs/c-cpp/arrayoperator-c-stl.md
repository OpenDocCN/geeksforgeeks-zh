# c++ STL 中的数组::运算符[]

> 原文:[https://www.geeksforgeeks.org/arrayoperator-c-stl/](https://www.geeksforgeeks.org/arrayoperator-c-stl/)

[数组](https://www.geeksforgeeks.org/array-class-c/)类一般比 C 风格的数组更高效、轻量、可靠。从 C++ 11 引入数组类为 C 风格的数组提供了一个更好的选择。

**array::operator[]**

该运算符用于引用运算符内部给出的*位置*处的元素。它与 at()函数类似，唯一的区别是 at()函数在位置不在数组大小的界限内时抛出一个超范围异常，而这个运算符导致**未定义的行为**。

**语法:**

```cpp
***arrayname[position]***
Parameters :
Position of the element to be fetched.
Returns :
Direct reference to the element at the given position.
```

示例:

```cpp
Input :  myarray = {1, 2, 3, 4, 5}
         myarray[2]
Output : 3

Input :  myarray = {1, 2, 3, 4, 5}
         myarray[4]
Output : 5
```

**错误和异常**
1。如果该位置不在数组中，它将显示未定义的行为。
2。否则它有一个无异常抛出保证。

## C++

```cpp
// CPP program to illustrate
// Implementation of [] operator
#include <iostream>
#include <array>
using namespace std;

int main()
{
    array<int,5> myarray{ 1, 2, 3, 4, 5 };
    cout << myarray[4];
    return 0;
}
```

输出:

```cpp
5
```

**应用程序**
给定一个整数数组，打印所有出现在偶数位置的整数。

```cpp
Input  :1, 2, 3, 4, 5
Output :1 3 5
*Explanation - 1, 3 and 5 are at position 0,2,4 which are even*
```

**算法**
1。运行一个循环，直到数组的大小。
2。检查该位置是否可被 2 整除，如果是，打印该位置的元素。

## C++

```cpp
// CPP program to illustrate
// Application of [] operator
#include <iostream>
#include <array>
using namespace std;

int main()
{
    array<int,5> myarray{ 1, 2, 3, 4, 5 };
    for(int i=0; i<myarray.size(); ++ i)
    {
        if(i%2==0){
            cout<<myarray[i];
            cout<<" ";
        }
    }
    return 0;
}
```

输出:

```cpp
1 3 5
```