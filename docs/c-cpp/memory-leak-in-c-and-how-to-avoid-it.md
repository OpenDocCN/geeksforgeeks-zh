# c++ 内存泄漏及如何避免？

> 原文:[https://www . geesforgeks . org/memory-leak-in-c-and-how-to-it/](https://www.geeksforgeeks.org/memory-leak-in-c-and-how-to-avoid-it/)

在 C++ 中，当程序员使用 [new 关键字](https://www.geeksforgeeks.org/new-vs-operator-new-in-cpp/)分配内存，而忘记使用 delete()函数或 [delete[]运算符](https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/)解除分配内存时，就会发生内存泄漏。在 C++ 中，使用错误的删除操作符会导致最严重的内存泄漏。
delete 运算符应该用于释放单个分配的内存空间，而 delete []运算符应该用于释放数据值数组。
**内存泄漏的缺点:**
如果一个程序有内存泄漏，那么它的内存使用量会讽刺性地增加，因为所有系统的内存都是有限的，而且内存成本很高。因此它会产生问题。
**c++ 内存泄漏示例**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Program with memory leak
#include <bits/stdc++.h>
using namespace std;

// function with memory leak
void func_to_show_mem_leak()
{
    int* ptr = new int(5);

    // body

    // return without deallocating ptr
    return;
}

// driver code
int main()
{

    // Call the function
    // to get the memory leak
    func_to_show_mem_leak();

    return 0;
}
```

**如何避免内存泄漏？**

*   不要手动管理内存，尽量使用智能指针。
*   使用 [std::string](https://www.geeksforgeeks.org/stdstring-class-in-c/) 代替 char *。std::string 类在内部处理所有的内存管理，并且速度快，优化好。
*   永远不要使用原始指针，除非它是为了与旧的 lib 接口。
*   在 C++ 中避免内存泄漏的最好方法是在程序级别尽可能少地进行新的/删除调用——最好是 NONE。任何需要动态内存的东西都应该被埋在一个 RAII 对象中，当它超出范围时释放内存。RAII 在构造函数中分配内存，在析构函数中释放内存，这样当变量离开当前作用域时，就保证了内存的释放。
*   通过 new 关键字分配内存，通过 delete 关键字释放内存，并在它们之间写入所有代码。

**处理内存泄漏的示例**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to
// illustrate how to avoid
// memory leak
#include <bits/stdc++.h>
using namespace std;

// function to see memory handling
void func_to_handle_mem_leak()
{
    int* ptr = new int(5);

    // body

    // Now delete pointer ptr using delete
    delete (ptr);
}

// Driver code
int main()
{

    // Call function to handle
    // the memory leak
    func_to_handle_mem_leak()

        return 0;
}
```

因此，**在 C++ 中总是写删除指针来匹配新的指针**，并且总是在这些新的和删除之间写代码，如上例所述。在上面的例子中，没有浪费内存，因为当我们从函数中出来时，我们通过使用 delete 函数来释放内存。