# c++ STL 中的 deque get _ 分配器

> 原文:[https://www.geeksforgeeks.org/deque-get_allocator-in-c-stl/](https://www.geeksforgeeks.org/deque-get_allocator-in-c-stl/)

**[【德格】](https://www.geeksforgeeks.org/deque-cpp-stl/):get _ 分配器()**是 C++ STL 中的一个内置函数，用来获取容器德格的分配器。
**语法:**

```cpp
Allocator_type get_allocator()

```

**参数:**此功能不接受任何参数。
**返回值:**返回一个与德格关联的分配器。

下面的程序说明了**deque::get _ 分配器()**函数的工作原理。
**例-1:**

```cpp
// CPP program to illustrate
// deque get_allocator()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    //'de' is object of 'deque'
    deque<int> de;

    //'allocator_type' is inherit in 'deque'
    //'d' is object of 'allocator_type'
    deque<int>::allocator_type d = de.get_allocator();

    // Comparing the Allocator with Pair<int, int>
    cout << "Is allocator Pair<int, int> : "
         << boolalpha
         << (d == allocator<pair<int, int> >());

    return 0;
}
```

**Output:**

```cpp
Is allocator Pair : true 
```

**示例-2:**

```cpp
// CPP program to illustrate
// deque get_allocator()
#include <bits/stdc++.h>
using namespace std;

int main(void)
{

    // Creating a container of type deque
    deque<int> de;

    // creating a pointer of type int
    int* array;

    // creating array using mylist get_allocator
    array = de.get_allocator().allocate(3);

    // inserting some data into array
    for (int i = 0; i < 3; i++)
        array[i] = i;

    // printing details of array
    for (int i = 0; i < 3; i++)
        cout << array[i] << " ";

    return 0;
}
```

**Output:**

```cpp
0 1 2

```