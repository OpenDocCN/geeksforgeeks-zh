# c++ STL 中的数组::max_size()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/arraymax _ size-c-STL/

[数组](https://www.geeksforgeeks.org/array-class-c/)类一般比 C 型数组更高效、轻量、可靠。从 C++ 11 引入数组类为 C 风格的数组提供了一个更好的选择。

**array::max_size()**

此函数返回数组容器可以包含的最大元素数。
如果是数组，size()和 max_size()函数总是返回相同的值

**语法:**

```cpp
*arrayname*.max_size()
Parameters :
No parameter is passed.
Returns :
It returns the maximum number of
elements that the array can contain.

```

示例:

```cpp
Input  : myarray = {1, 2, 3, 4, 5, 6, 7, 8, 9, 0};
         myarray.max_size();
Output : 10

Input  : myarray = {1, 2, 3, 4, 5};
         myarray.max_size();
Output : 5

```

**错误和异常**

```cpp
1\. It throws an error if a parameter is passed.
2\. It has a no exception throw guarantee otherwise.

```

```cpp
// CPP program to illustrate
// Implementation of max_size() function
#include <array>
#include <iostream>
using namespace std;

int main()
{
    array<int, 5> myarray{ 1, 2, 3, 4, 5 };
    cout << myarray.max_size();
    return 0;
}
```

输出:

```cpp
5

```