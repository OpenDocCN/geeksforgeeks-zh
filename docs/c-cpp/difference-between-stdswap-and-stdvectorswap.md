# STD::swap 和 std::vector::swap 的区别

> 原文:[https://www . geesforgeks . org/difference-stdswap-and-stdvectorswap/](https://www.geeksforgeeks.org/difference-between-stdswap-and-stdvectorswap/)

**std::swap** 是用于交换给定值的通用函数，而 **std::vector::swap** 是可以交换两个不同向量容器的所有内容的专用函数。
下面是 std::swap 和 std::vector::swap 之间的一些主要区别，

<figure class="table">

| 标准::交换 | 标准::矢量::交换 |
| STD::swap () is a built-in function in C++ STL, which exchanges the values of any two variables passed to it as parameters. | The STD::vector::swap () function is used to exchange the entire contents of one vector with another vector of the same type. |
| If std::swap () function is used to exchange two vectors A and B, it will call std::swap algorithm of std::vector, which in turn calls A.swap(B) and exchanges contents. | The STD::vector::swap function exchanges the contents of one vector with another vector. It exchanges addresses of two vectors (that is, containers exchange references to their data), instead of exchanging each element one by one, which is done in a constant time of 0(1). |
| The overload of std::swap of the adapter was introduced in C++ 11\. Earlier versions of C++ will require linear time complexity to exchange vectors. | STD::vector:: The exchange function will always exchange the contents of the vector in a constant time. |

</figure>

实际上，这两个函数将在 O(1)时间内交换向量的内容，并给出相同的性能。为了保持一致性，最好使用 std::swap。

**程序 1** :用 std::swap()说明两个向量的交换。

## 卡片打印处理机（Card Print Processor 的缩写）

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

**程序 2** :用 std::vector::swap()说明两个向量的交换。

## 卡片打印处理机（Card Print Processor 的缩写）

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