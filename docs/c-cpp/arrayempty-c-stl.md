# 数组::空()在 C++ STL 中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/array empty-c-STL/

[数组](https://www.geeksforgeeks.org/array-class-c/)类一般比 C 风格数组更高效、轻量、可靠。从 C++ 11 引入数组类为 C 风格的数组提供了一个更好的选择。

**array::empty()**

empty()函数用于检查数组容器是否为空。

**语法:**

```cpp
*arrayname*.empty()
Parameters :
No parameters are passed.
Returns :
True, if array is empty
False, Otherwise

```

示例:

```cpp
Input  : myarray{1, 2, 3, 4, 5};
         myarray.empty();
Output : False

Input  : myarray{};
         myarray.empty();
Output : True

```

**错误和异常**

1.它有一个无异常抛出保证。
2。传递参数时显示错误。

```cpp
// Non Empty array example
// CPP program to illustrate
// Implementation of empty() function
#include <array>
#include <iostream>
using namespace std;

int main()
{
    array<int, 5> myarray{ 1, 2, 3, 4 };
    if (myarray.empty()) {
        cout << "True";
    }
    else {
        cout << "False";
    }
    return 0;
}
```

输出:

```cpp
False

```

```cpp
// Empty array example
// CPP program to illustrate
// Implementation of empty() function
#include <array>
#include <iostream>
using namespace std;

int main()
{
    array<int, 0> myarray;
    if (myarray.empty()) {
        cout << "True";
    }
    else {
        cout << "False";
    }
    return 0;
}
```

输出:

```cpp
True

```