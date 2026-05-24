# c++ STL 中的数组::begin()和数组::end()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/arraybegin-arrayend-c-STL/

[数组](https://www.geeksforgeeks.org/array-class-c/)类一般比 C 型数组更高效、轻量、可靠。从 C++ 11 引入数组类为 C 风格的数组提供了一个更好的选择。

**array::begin()**

begin()函数用于返回指向数组容器第一个元素的迭代器。begin()函数**返回一个双向迭代器**到容器的第一个元素。
**语法:**

```cpp
***arrayname.begin()***
Parameters :
No parameters are passed.

Returns :
This function returns a bidirectional
iterator pointing to the first element.
```

示例:

```cpp
Input  : myarray{1, 2, 3, 4, 5};
Output : *returns an iterator to the element 1*

Input  : myarray{8, 7};         
Output : *returns an iterator to the element 8*
```

**错误和异常**
1。它有一个无异常抛出保证。
2。传递参数时显示错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of begin() function
#include <array>
#include <iostream>
using namespace std;

int main()
{
    // declaration of array container
    array<int, 5> myarray{ 1, 2, 3, 4, 5 };

    // using begin() to print array
    for (auto it = myarray.begin();
         it != myarray.end(); ++ it)
        cout << ' ' << *it;

    return 0;
}
```

**输出:**

```cpp
1 2 3 4 5
```

**array::end()**

end()返回指向数组容器中结束元素的迭代器。
**语法:**

```cpp
***arrayname.end()***
Parameters :
No parameters are passed.

Returns :
This function returns a bidirectional
iterator pointing to the past-the-end element.
```

示例:

```cpp
Input  : myarray{1, 2, 3, 4, 5};
Output : *returns an iterator to the element next to 5 i.e,. some garbage value*

Input  : myarray{8, 7};
Output : *returns an iterator to the element* next to *7* i.e,. some garbage value
```

**错误和异常**
1。它有一个无异常抛出保证。
2。传递参数时显示错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of end() function
#include <array>
#include <iostream>
using namespace std;

int main()
{
    // declaration of array container
    array<int, 5> myarray{ 1, 2, 3, 4, 5 };

    // using end() to print array
    for (auto it = myarray.begin();
         it != myarray.end(); ++ it)
        cout << ' ' << *it;

      auto it = myarray.end();
      cout << "\n myarray.end(): " << *it << " [some garbage value]";
    return 0;
}
```

**输出:**

```cpp
1 2 3 4 5
myarray.end(): 0 [some garbage value]
```