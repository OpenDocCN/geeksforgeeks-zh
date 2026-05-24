# C/c++ 中迭代器和指针的区别，示例

> 原文:[https://www . geeksforgeeks . org/iterators-and-pointers-in-c-with-examples/](https://www.geeksforgeeks.org/difference-between-iterators-and-pointers-in-c-c-with-examples/)

[**指针**](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/) **:** 指针是一个变量，它包含另一个变量的地址，即该变量的内存位置的地址。像任何变量或常量一样，在使用指针存储任何变量地址之前，我们必须声明一个指针。
**语法:**

```cpp
type* var_name;
```

**示例:**

## C

```cpp
// The output of this program can be different
// in different runs. Note that the program
// prints address of a variable and a variable
// can be assigned different address in different
// runs.
#include <stdio.h>

int main()
{
    int x;

    // Prints address of x
    printf("%p", &x);

    return 0;
}
```

**Output:** 

```cpp
0x7ffcac5ae824
```

[**迭代器**](https://www.geeksforgeeks.org/introduction-iterators-c/) **:** 迭代器是任何对象，它指向元素范围(如数组或容器)中的某个元素，能够遍历该范围的元素。
**语法:**

```cpp
type_container :: iterator var_name;
```

**示例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate iterators
#include <iostream>
#include <vector>
using namespace std;
int main()
{
    // Declaring a vector
    vector<int> v = { 1, 2, 3 };

    // Declaring an iterator
    vector<int>::iterator i;

    int j;

    cout << "Without iterators = ";

    // Accessing the elements without using iterators
    for (j = 0; j < 3; ++ j) {
        cout << v[j] << " ";
    }

    cout << "\nWith iterators = ";

    // Accessing the elements using iterators
    for (i = v.begin(); i != v.end(); ++ i) {
        cout << *i << " ";
    }

    // Adding one more element to vector
    v.push_back(4);

    cout << "\nWithout iterators = ";

    // Accessing the elements without using iterators
    for (j = 0; j < 4; ++ j) {
        cout << v[j] << " ";
    }

    cout << "\nWith iterators = ";

    // Accessing the elements using iterators
    for (i = v.begin(); i != v.end(); ++ i) {
        cout << *i << " ";
    }

    return 0;
}
```

**Output:** 

```cpp
Without iterators = 1 2 3 
With iterators = 1 2 3 
Without iterators = 1 2 3 4 
With iterators = 1 2 3 4
```

**迭代器和指针的区别:**
迭代器和指针的相似之处在于，我们可以取消引用它们来获取一个值。然而，主要的区别如下:

<figure class="table">

| needle | iterator |
| --- | --- |
| A pointer holds an address in memory. | An iterator can hold pointers, but it may be something more complicated. For example, an iterator can iterate data on a file system, data distributed on many machines, or locally generated data programmatically.
A good example is the iterator on the linked list. The iterator will traverse the elements on the nodes whose addresses may be scattered in the list. |
| We can perform simple arithmetic operations on pointers, such as incrementing, decrementing, adding integers, etc. | Not all iterators allow these operations. For example, we can't reduce forward iterators or add integers to non-random access iterators. |
| T * type pointers can point to any T-type objects. | Iterators are more limited. For example, vector:: iterators can only refer to double precision in vector containers. |
| We can use **to delete** | To delete the pointer, because the iterator refers to the object in the container. Unlike the pointer, the iterator does not have the concept of **deleting** . (The container is responsible for memory management. )
 |

</figure>