# C++ STL 中的 unordered_multiset::get_allocator

> 原文：[https://www.geeksforgeeks.org/unordered_multiset-get_allocator-in-c-stl/](https://www.geeksforgeeks.org/unordered_multiset-get_allocator-in-c-stl/)

`unordered_multiset::get_allocator()` 函数是 C++ 中的一个 STL 函数，用于在程序中包含 `unordered_multiset` 头文件。该函数获取存储的分配器对象，并返回用于构造容器的分配器对象。这是一个公共成员函数。

## 语法

```cpp
allocator_type get_allocator() const;
```

这里，`allocator_type` 是容器使用的分配器的类型。

## 参数

不接受任何参数。

## 返回值

返回 `allocator_type`。

下面程序举例说明了 C++ STL 中的 `get_allocator` 方法：

## 程序

```cpp
// c++ program to understand 'unordered_multiset_get_allocator'
#include <iostream>
#include <unordered_set>
using namespace std;

// main() method
int main() 
{

//'m' is object of 'unordered_set'
    unordered_multiset<int> m;

//'allocator_type' is inherit in 'unordered_multiset'
    //'t' is object of 'allocator_type'
    //'get_allocator()' is member of 'unordered_set'
    unordered_multiset<int>::allocator_type t = m.get_allocator();

// Comparing the Allocator with 'Pair<int, int>'
    cout << "allocator is : "
        << boolalpha << (t == allocator<std::pair<int, int> >());

return (0);
}
```

## 输出

```cpp
allocator is : true
```

## 复杂度

执行运算需要恒定的复杂度时间。