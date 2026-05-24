# c++ 中的 std::分配器()，示例

> 原文:[https://www . geeksforgeeks . org/std 分配器-in-cpp-with-examples/](https://www.geeksforgeeks.org/stdallocator-in-cpp-with-examples/)

分配器是负责封装内存管理的对象。 **std::分配器**在你想分两步进行分配和施工的时候使用。当分两步完成单独的销毁和解除分配时，也可以使用它。

C++ 中的所有 STL 容器都有一个默认为 **std::分配器**的类型参数分配器。默认分配器只是使用 new 和 delete 操作符来获取和释放内存。

**申报:**

```cpp
template <class T> class allocator;
```

与 std::分配器()关联的成员函数:

1.  **地址:**虽然在 C++ 20 中去掉了，但是用于获取对象的地址。
2.  **构造:**用于构造一个物体。它也在 C++ 20 中被移除。
3.  **销毁:**用于销毁已分配存储中的对象。它也在 C++ 20 中被移除。
4.  **max_size:** 返回支持的最大分配大小。它在 C++ 17 中被否决，在
    C++ 20 中被删除。
5.  **分配:**用于内存分配。
6.  **解除分配:**用于内存的解除分配。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program for illustration
// of std::allocator() function
#include <iostream>
#include <memory>
using namespace std;
int main()
{

    // allocator for integer values
    allocator<int> myAllocator;

    // allocate space for five ints
    int* arr = myAllocator.allocate(5);

    // construct arr[0] and arr[3]
    myAllocator.construct(arr, 100);
    arr[3] = 10;

    cout << arr[3] << endl;
    cout << arr[0] << endl;

    // deallocate space for five ints
    myAllocator.deallocate(arr, 5);

    return 0;
}
```

**Output:**

```cpp
10
100

```

**程序 2:**

```cpp
// C++ program for illustration
// of std::allocator() function
#include <iostream>
#include <memory>
#include <string>
using namespace std;

int main()
{

    // allocator for string values
    allocator<string> myAllocator;

    // allocate space for three strings
    string* str = myAllocator.allocate(3);

    // construct these 3 strings
    myAllocator.construct(str, "Geeks");
    myAllocator.construct(str + 1, "for");
    myAllocator.construct(str + 2, "Geeks");

    cout << str[0] << str[1] << str[2];

    // destroy these 3 strings
    myAllocator.destroy(str);
    myAllocator.destroy(str + 1);
    myAllocator.destroy(str + 2);

    // deallocate space for 3 strings
    myAllocator.deallocate(str, 3);
}
```

**Output:**

```cpp
GeeksforGeeks

```

**使用 std::分配器的优势**

1.  分配器是 STL 容器的内存分配器。该容器可以将内存分配和取消分配与其元素的初始化和销毁分开。因此，向量向量的 vec.reserve(n)调用只为至少 n 个元素分配内存。不会执行每个元素的构造函数。
2.  分配器可以根据你需要的容器进行调整，例如，你只是偶尔想分配的 vector。
3.  相反， [new](https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/) 不允许控制调用哪些构造函数，只是同时构造所有对象。这是 std::分配器相对于新的优势