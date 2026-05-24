# c++ STL 中的数组::填充()和数组::交换()

> 原文:[https://www.geeksforgeeks.org/arrayfill-arrayswap-c-stl/](https://www.geeksforgeeks.org/arrayfill-arrayswap-c-stl/)

[数组](https://www.geeksforgeeks.org/array-class-c/)类一般比 C 风格数组更高效、轻量、可靠。从 C++ 11 引入数组类为 C 风格的数组提供了一个更好的选择。

**array::fill()**

该函数用于为数组容器的所有元素设置一个公共值。

**语法:**

```cpp
*arrayname*.fill(*value*)
Parameters :
The value to be set for all the elements of
the container is passed as parameter.
Result :
All the elements of the container are
set to be equal to the parameter passed.

```

示例:

```cpp
Input  : myarray = {1, 2, 3, 4}
         myarray.fill(5);
Output : myarray = {5, 5, 5, 5}

Input  : myarray = {1, 2, 3, 4, 5, 6, 7}
         myarray.fill(2);
Output : myarray = {2, 2, 2, 2, 2, 2, 2}

```

**错误和异常**

1.如果赋值操作抛出一些错误，它就会抛出一个错误。
2。否则它有一个基本的无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of fill() function
#include <array>
#include <iostream>
using namespace std;

int main()
{
        // array container declaration
    array<int, 4> myarray{ 1, 2, 3, 4 };

        // Using fill() function to 
    myarray.fill(5);

        // printing the array
    for(auto it=myarray.begin(); it<myarray.end(); ++ it)
        cout<<*it<<" ";
    return 0;
}
```

输出:

```cpp
5 5 5 5

```

**array::swap()**

此函数用于将一个数组的内容与另一个相同类型和大小的数组进行交换。

**语法:**

```cpp
*arrayname1*.swap(*arrayname2*)
Parameters :
The name of the array with which
the contents have to be swapped.
Result :
All the elements of the 2 array are swapped.

```

示例:

```cpp
Input  : myarray1 = {1, 2, 3, 4}
         myarray2 = {3, 5, 7, 9}
         myarray1.swap(myarray2);
Output : myarray1 = {3, 5, 7, 9}
         myarray2 = {1, 2, 3, 4}

Input  : myarray1 = {1, 3, 5, 7}
         myarray2 = {2, 4, 6, 8}
         myarray1.swap(myarray2);
Output : myarray1 = {2, 4, 6, 8}
         myarray2 = {1, 3, 5, 7}

```

**错误和异常**

1.如果数组不是同一类型，它将引发错误。
2。如果数组大小不同，它将引发错误。
2。否则它有一个基本的无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of swap() function
#include <array>
#include <iostream>
using namespace std;

int main()
{
        // array container declaration
    array<int, 4> myarray1{ 1, 2, 3, 4 };
    array<int, 4> myarray2{ 3, 5, 7, 9 };

        // using swap() function to swap elements of arrays
    myarray1.swap(myarray2);

        // printing the first array
    cout<<"myarray1 = ";
    for(auto it=myarray1.begin(); it<myarray1.end(); ++ it)
        cout<<*it<<" ";

        // printing the second array
    cout<<endl<<"myarray2 = ";
    for(auto it=myarray2.begin(); it<myarray2.end(); ++ it)
        cout<<*it<<" ";
    return 0;
}
```

输出:

```cpp
myarray1 = 3 5 7 9 
myarray2 = 1 2 3 4 

```