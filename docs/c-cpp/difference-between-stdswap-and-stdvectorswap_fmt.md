# std::swap 和 std::vector::swap 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-stdswap-and-stdvectorswap/](https://www.geeksforgeeks.org/difference-between-stdswap-and-stdvectorswap/)

`std::swap` 是用于交换给定值的通用函数，而 `std::vector::swap` 是可以交换两个不同向量容器的所有内容的专用函数。
下面是 `std::swap` 和 `std::vector::swap` 之间的一些主要区别，

| std::swap | std::vector::swap |
| --- | --- |
| `std::swap()` 是 C++ STL 中的一个内置函数，用于交换传递给它的任何两个参数的值。 | `std::vector::swap()` 函数用于交换一个向量与另一个相同类型向量的全部内容。 |
| 如果使用 `std::swap()` 函数来交换两个向量 A 和 B，它将调用 `std::vector` 的 `std::swap` 算法，进而调用 `A.swap(B)` 并交换内容。 | `std::vector::swap` 函数交换一个向量与另一个向量的内容。它交换两个向量的地址（即容器交换对其数据的引用），而不是逐个交换每个元素，这在 `O(1)` 的常数时间内完成。 |
| 适配器的 `std::swap` 重载是在 C++ 11 中引入的。早期版本的 C++ 交换向量需要线性时间复杂度。 | `std::vector::swap` 函数将始终在常数时间内交换向量的内容。 |

实际上，这两个函数都将在 `O(1)` 时间内交换向量的内容，并给出相同的性能。为了保持一致性，最好使用 `std::swap`。

**程序 1**：用 `std::swap()` 说明两个向量的交换。

### CPP 程序（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate swapping
// of two vectors using std::swap()

#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> v1 = { 1, 2, 3 };
    vector<int> v2 = { 4, 5, 6 };

    // swapping the above two vectors
    // by traversing and swapping each element
    for (int i = 0; i < 3; i++) {
        swap(v1[i], v2[i]);
    }

    // print vector v1
    cout << "Vector v1 = ";
    for (int i = 0; i < 3; i++) {
        cout << v1[i] << " ";
    }

    // print vector v2
    cout << "\nVector v2 = ";
    for (int i = 0; i < 3; i++) {
        cout << v2[i] << " ";
    }

    return 0;
}
```

**Output:**

```cpp
Vector v1 = 4 5 6 
Vector v2 = 1 2 3
```

**程序 2**：用 `std::vector::swap()` 说明两个向量的交换。

### CPP 程序（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate swapping
// of two vectors using std::vector::swap()

#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> v1 = { 1, 2, 3 };
    vector<int> v2 = { 4, 5, 6 };

    // swapping the above two vectors
    // using std::vector::swap
    v1.swap(v2);

    // print vector v1
    cout << "Vector v1 = ";
    for (int i = 0; i < 3; i++) {
        cout << v1[i] << " ";
    }

    // print vector v2
    cout << "\nVector v2 = ";
    for (int i = 0; i < 3; i++) {
        cout << v2[i] << " ";
    }

    return 0;
}
```

**Output:**

```cpp
Vector v1 = 4 5 6 
Vector v2 = 1 2 3
```