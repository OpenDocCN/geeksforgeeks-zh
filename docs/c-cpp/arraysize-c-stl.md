# c++ STL 中的数组::大小()

> 原文:[https://www.geeksforgeeks.org/arraysize-c-stl/](https://www.geeksforgeeks.org/arraysize-c-stl/)

[数组](https://www.geeksforgeeks.org/array-class-c/)类一般比 C 风格数组更高效、轻量、可靠。从 C++ 11 引入数组类为 C 风格的数组提供了一个更好的选择。

**array::size()**

size()函数用于返回列表容器的大小或列表容器中的元素数量。

**语法:**

```cpp
*arrayname*.size()
Parameters :
No parameters are passed.
Returns :
Number of elements in the container.
```

示例:

```cpp
Input  : myarray{1, 2, 3, 4, 5};
         myarray.size();
Output : 5

Input  : myarray{};
         myarray.size();
Output : 0
```

**错误和异常**

1.它有一个无异常抛出保证。
2。传递参数时显示错误。

```cpp
// CPP program to illustrate
// Implementation of size() function
#include <iostream>
#include <array>
using namespace std;

int main()
{
    array<int,5> myarray{ 1, 2, 3, 4, 5 };
    cout << myarray.size();
    return 0;
}
```

输出:

```cpp
5
```