# c++ 中的 std::tuple_element()和 std::tuple_size()，示例

> 原文:[https://www . geesforgeks . org/stdtuple _ element-and-stdtuple _ size-in-c-with-examples/](https://www.geeksforgeeks.org/stdtuple_element-and-stdtuple_size-in-c-with-examples/)

一个 [元组](https://www.geeksforgeeks.org/tuples-in-c/) 是一个 [对象](https://www.geeksforgeeks.org/c-classes-and-objects/) 可以容纳多个元素。元素可以不同 [数据类型](https://www.geeksforgeeks.org/c-data-types/) 。元组的元素按照被访问的顺序被初始化为 [参数](https://www.geeksforgeeks.org/command-line-arguments-in-c-cpp/) 。

> 函数-
> **tuple_element()** 和 **tuple_size()**
> 仅使用 **tuple_like** 接口为元素定义。

**tuple _ element():**
[c++ 函数](https://www.geeksforgeeks.org/functions-in-c/) **tuple_element(array)** 使用类似元组的接口提供对数组元素类型的编译型索引访问。

**语法-**

```cpp
template< size_t I, class T, size_t N >
struct tuple_element<I, array<T, N> >;
```

**参数-**

```cpp
T − type for which the tuple element is obtained.
I − index of the element.
N − the size of the array.
```

**示例-**
下面是实现 tuple_element(数组)概念的 C++ 程序-

## C++

```cpp
// C++ program to implement
// the above approach

#include <array>
#include <iostream>
#include <tuple>
#include <type_traits>
using namespace std;

// Driver code
int main()
{
    // Define array
    array<int, 3> data{ 3, 5, 10 };

    // Type of element at index 0
    using type = std::tuple_element<0,
                                    decltype(data)>::type;

    // Compare type with int
    // returns true
    cout << std::is_same<type,
                         int>::value
         << '\n';

    // Compare type with char
    // returns false
    cout << std::is_same<type,
                         char>::value
         << '\n';
}
```

**Output**

```cpp
1
0
```

**tuple _ size():**
[c++ ](https://www.geeksforgeeks.org/c-plus-plus/)函数 **tuple_size(数组)**返回[数组](https://www.geeksforgeeks.org/arrays-in-c-cpp/)中存在的元素总数。

**语法-**

```cpp
template< class T, size_t N >
class tuple_size< array<T, N> > :
 integral_constant<size_t, N>
{ };
```

**参数-**

```cpp
T − type for which the tuple size is obtained.
```

**示例-**
下面是实现 tuple_size()概念的 C++ 程序-

## C++

```cpp
// C++ program to implement
// the above approach
#include <array>
#include <iostream>
using namespace std;

// Driver code
int main()
{
    // Array of size 6
    array<int, 6> a;

    // Find size using tuple_size
    cout << tuple_size<decltype(a)>::value;
    return 0;
}
```

**Output**

```cpp
6
```