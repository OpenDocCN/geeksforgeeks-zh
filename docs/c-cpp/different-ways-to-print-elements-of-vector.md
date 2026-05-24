# 打印矢量元素的不同方式

> 原文:[https://www . geeksforgeeks . org/不同方式打印矢量元素/](https://www.geeksforgeeks.org/different-ways-to-print-elements-of-vector/)

[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)与[动态数组](https://www.geeksforgeeks.org/how-do-dynamic-arrays-work/)相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。向量的元素被放置在[连续存储](https://www.geeksforgeeks.org/difference-between-contiguous-and-noncontiguous-memory-allocation/)中，以便可以使用[迭代器](https://www.geeksforgeeks.org/iterators-c-stl/)访问和遍历它们。在向量中，数据被插入到末尾。在末端插入需要不同的时间，因为有时可能需要扩展[阵列](https://www.geeksforgeeks.org/introduction-to-arrays/)。移除最后一个元素只需要恒定的时间，因为不会发生调整大小的情况。在开始或中间插入和擦除在时间上是线性的。

### **<u>在</u>**[**<u>c++ </u>**](https://www.geeksforgeeks.org/c-plus-plus/)中打印 Vector 所有元素的不同方式

**通过使用** [**重载**](https://www.geeksforgeeks.org/operator-overloading-c/)**[**<<运算符**](https://www.geeksforgeeks.org/left-shift-right-shift-operators-c-cpp/) **:** 通过在全局范围内重载< <运算符作为[模板](https://www.geeksforgeeks.org/templates-cpp/)函数，可以通过逐个迭代来打印向量的所有元素。**

**下面是实现上述概念的 C++ 程序:**

## **c++**

```cpp
// C++ program to print the elements
// of the vector
#include <iostream>
#include <vector>
using namespace std;

template <typename S>
ostream& operator<<(ostream& os,
                    const vector<S>& vector)
{
    // Printing all the elements
    // using <<
    for (auto element : vector) {
        os << element << " ";
    }
    return os;
}

// Driver Code
int main()
{
    // vector containing integer elements
    vector<int> A = { 10, 20, 30,
                      40, 50, 60 };

    cout << A << endl;

    return 0;
}
```

****输出****

```cpp
10 20 30 40 50 60 
```