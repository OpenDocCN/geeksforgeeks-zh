# C/C++ 中迭代器和指针的区别，示例

> 原文: [https://www.geeksforgeeks.org/difference-between-iterators-and-pointers-in-c-c-with-examples/](https://www.geeksforgeeks.org/difference-between-iterators-and-pointers-in-c-c-with-examples/)

## 指针

[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)是一个变量，它包含另一个变量的地址，即该变量的内存位置的地址。像任何变量或常量一样，在使用指针存储任何变量地址之前，我们必须声明一个指针。

**语法:**

```cpp
type* var_name;
```

**示例:**

### C

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

## 迭代器

[迭代器](https://www.geeksforgeeks.org/introduction-iterators-c/)是任何对象，它指向元素范围(如数组或容器)中的某个元素，能够遍历该范围的元素。

**语法:**

```cpp
type_container :: iterator var_name;
```

**示例:**

### C++

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

## 迭代器和指针的区别

迭代器和指针的相似之处在于，我们可以取消引用它们来获取一个值。然而，主要的区别如下:

| 特性 | 指针 | 迭代器 |
| --- | --- | --- |
| 本质 | 指针保存内存中的一个地址。 | 迭代器可以包含指针，但它可能是更复杂的东西。例如，迭代器可以遍历文件系统上的数据、分布在多台机器上的数据，或以编程方式本地生成的数据。链表迭代器就是一个很好的例子。迭代器将遍历节点上的元素，这些节点的地址可能在链表中是分散的。 |
| 操作 | 我们可以对指针执行简单的算术运算，例如递增、递减、加整数等。 | 并非所有迭代器都允许这些操作。例如，我们不能对前向迭代器进行递减，也不能对非随机访问迭代器添加整数。 |
| 类型安全 | `T*` 类型的指针可以指向任何 `T` 类型的对象。 | 迭代器限制更多。例如，`vector::iterator` 只能引用 `vector` 容器中的 `double` 精度元素。 |
| 内存管理 | 我们可以使用 `delete` 来删除指针。 | 不能删除迭代器，因为迭代器引用的是容器中的对象。与指针不同，迭代器没有 `删除` 的概念。（容器负责内存管理。） |