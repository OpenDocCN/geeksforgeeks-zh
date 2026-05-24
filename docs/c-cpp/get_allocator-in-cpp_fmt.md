## C++ 中的 `get_allocator()`

> 原文：[https://www.geeksforgeeks.org/get_allocator-in-cpp/](https://www.geeksforgeeks.org/get_allocator-in-cpp/)

在 STL 中，容器可以动态改变大小。分配器是负责动态内存分配/解除分配的对象。`get_allocator()` 用于分配内存块。它返回与容器关联的分配器对象的副本。在 [`vector`](https://www.geeksforgeeks.org/vector-in-cpp-stl/)、[`map`](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)、[`list`](https://www.geeksforgeeks.org/list-cpp-stl/)、[`set`](https://www.geeksforgeeks.org/set-in-cpp-stl/) 库中定义。

**语法：**

```cpp
allocator_type get_allocator() const;
```

> **参数使用：**
> 这个成员函数不需要传递任何参数。
>
> **返回类型：**
> 它返回与向量相关联的分配器对象的副本。
>
> **错误和异常：**
> 从不抛出异常，所以我们不需要围绕它进行任何尝试。
>
> **时间复杂度：**
> 常数 `O(1)`。

下面的程序说明了该功能的工作原理。

### 1. `std::vector::get_allocator()`
它返回与 [`vector`](https://www.geeksforgeeks.org/vector-in-cpp-stl/) 关联的分配器对象的副本。

```cpp
// C++ program to show working
// of get_allocator function
#include <iostream>
#include <vector>

using namespace std;

// Function for allocating
char* Allocate(vector<char> arr, int size)
{
  // allocate space for size(s) elements
  return arr.get_allocator().allocate(size);
}

void Construct(vector<char> arr,
               char* point, int size)
{
    for (int iter = 0; iter < size; ++ iter)

// construct values in-place on the array:
      arr.get_allocator().construct(&point[iter],
                                    iter + 97);
}

// Function for Deallocating
void deAllocate(vector<char> arr,
                char* point, int size)
{
    for (int iter = 0; iter < size; ++ iter)
        arr.get_allocator().destroy(&point[iter]);

// free allocated memory
    arr.get_allocator().deallocate(point, size);
}

// Driver code
int main()
{
    vector<char> array;
    char* pointer;
    int size = 8;

    pointer = Allocate(array, size);
    Construct(array, pointer, size);

    cout << "Array elements:  ";
    for (int iter = 0; iter < size; ++ iter)
        cout << pointer[iter] << " ";

    deAllocate(array, pointer, size);

    return 0;
}
```

**Output：**

```cpp
Array elements:  a b c d e f g h
```

### 2. `std::list::get_allocator()`
它返回与 [`list`](https://www.geeksforgeeks.org/list-cpp-stl/) 相关联的分配器对象的副本。

```cpp
// C++ program to show working
// of get_allocator function
#include <iostream>
#include <list>

using namespace std;

// Function for allocating
char* Allocate(list<char> arr, int size)
{
  // allocate space for size(s) elements
  return arr.get_allocator().allocate(size);
}

void Construct(list<char> arr,
               char* point, int size)
{
    for (int iter = 0; iter < size; ++ iter)

// construct values in-place on the array:
      arr.get_allocator().construct(&point[iter],
                                    iter + 97);
}

// Function for Deallocating
void deAllocate(list<char> arr,
                char* point, int size)
{
    for (int iter = 0; iter < size; ++ iter)
        arr.get_allocator().destroy(&point[iter]);

// free allocated memory
    arr.get_allocator().deallocate(point, size);
}

// Driver code
int main()
{
    list<char> array;
    char* pointer;
    int size = 8;

    pointer = Allocate(array, size);
    Construct(array, pointer, size);

    cout << "Array elements:  ";
    for (int iter = 0; iter < size; ++ iter)
        cout << pointer[iter] << " ";

    deAllocate(array, pointer, size);

    return 0;
}
```

**Output：**

```cpp
Array elements:  a b c d e f g h
```

### 3. `std::set::get_allocator()`
它返回与 [`set`](https://www.geeksforgeeks.org/set-in-cpp-stl/) 关联的分配器对象的副本。

```cpp
// C++ program to show working
// of get_allocator function
#include <iostream>
#include <set>

using namespace std;

// Function for allocating
char* Allocate(set<char> arr, int size)
{
  // allocate space for size(s) elements
  return arr.get_allocator().allocate(size);
}

void Construct(set<char> arr,
               char* point, int size)
{
    for (int iter = 0; iter < size; ++ iter)

// construct values in-place on the array:
      arr.get_allocator().construct(&point[iter],
                                    iter + 97);
}

// Function for Deallocating
void deAllocate(set<char> arr,
                char* point, int size)
{
    for (int iter = 0; iter < size; ++ iter)
        arr.get_allocator().destroy(&point[iter]);

// free allocated memory
    arr.get_allocator().deallocate(point, size);
}

// Driver code
int main()
{
    set<char> array;
    char* pointer;
    int size = 8;

    pointer = Allocate(array, size);
    Construct(array, pointer, size);

    cout << "Array elements:  ";
    for (int iter = 0; iter < size; ++ iter)
        cout << pointer[iter] << " ";

    deAllocate(array, pointer, size);

    return 0;
}
```

**Output：**

```cpp
Array elements:  a b c d e f g h
```

参考文献：[http://www.cplusplus.com/reference/vector/vector/get_allocator/](http://www.cplusplus.com/reference/vector/vector/get_allocator/)