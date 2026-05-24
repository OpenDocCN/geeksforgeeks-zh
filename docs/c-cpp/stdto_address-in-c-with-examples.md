# 标准::to_address 用 C++ 举例

> 原文:[https://www . geesforgeks . org/stdto _ address-in-c-with-examples/](https://www.geeksforgeeks.org/stdto_address-in-c-with-examples/)

C++ 20 中引入的 **std::to_address** 用于获取指定指针所表示的地址，而不构成对指针的引用。现有的 **std::addressof** 不能做 *std::addressof(*ptr)* ，因为 **ptr* 并不总是一个对象。 **std::to_address** 为我们解决了这些问题。

**语法:**

```cpp
template class Ptr
constexpr auto to_address(const Ptr& p) noexcept;

template class T
constexpr T* to_address(T* p) noexcept;

```

**参数:**这个方法接受一个参数 **p** ，这个参数是需要找到地址的花式或原始指针。

**返回值:**该方法返回代表指针 p 地址的**原始指针**

以下示例演示了 std::address
**示例 1** 的用法:

```cpp
// C++ code to show
// the use of std::address

#include <iostream>
#include <memory>
using namespace std;

// Allocate memory and return
// the pointer to that memory
template <class A>
auto allocator_new(A& a)
{
    auto p = a.allocate(1);
    try {
        allocator_traits<A>::construct(
            a, to_address(p));
    }
    catch (...) {
        a.deallocate(p, 1);
        throw;
    }

    cout << "Pointer to Memory allocated: "
         << p << endl;
    return p;
}

// Delete memory using
// pointer to that memory
template <class A>
void allocator_delete(
    A& a,
    typename allocator_traits<A>::pointer p)
{
    allocator_traits<A>::destroy(
        a, to_address(p));
    a.deallocate(p, 1);
    cout << "Pointer to Memory deleted: "
         << p << endl;
}

// Driver code
int main()
{
    allocator<int> a;
    auto p = allocator_new(a);
    allocator_delete(a, p);
}
```

**输出:**

```cpp
Pointer to Memory allocated: 0x1512c20
Pointer to Memory deleted: 0x1512c20

```

**例 2:**

```cpp
// C++ code to show
// the use of std::address

#include <iostream>
#include <memory>
using namespace std;

int main()
{

    // Make a unique pointer and
    // use to_address to get its address
    // from heap memory
    cout << "Using unique pointers\n\n";
    auto ptr = make_unique<int>(15);
    cout << "Address of pointer to 15: "
         << to_address(ptr) << "\n";

    auto ptr1 = make_unique<int>(17);
    cout << "Address of pointer to 17: "
         << to_address(ptr1) << "\n";

    // Use to_address to get the
    // address of a dumb pointer
    // from stack memory
    cout << "\nUsing dumb pointers\n\n";

    int i = 17;
    cout << "Address of pointer to 17: "
         << to_address(&i) << "\n";

    int j = 18;
    cout << "Address of pointer to 18: "
         << to_address(&j) << "\n";

    return 0;
}
```

**输出:**

```cpp
Using unique pointers

Address of pointer to 15: 0x181ec30
Address of pointer to 17: 0x181ec50

Using dumb pointers

Address of pointer to 17: 0x7fff6b454398
Address of pointer to 18: 0x7fff6b45439c

```

**参考:**T2】https://en.cppreference.com/w/cpp/memory/to_address