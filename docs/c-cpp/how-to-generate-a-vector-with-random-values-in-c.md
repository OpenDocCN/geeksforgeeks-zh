# 如何在 C++ 中生成一个随机取值的向量？

> 原文:[https://www . geeksforgeeks . org/如何生成带有 c 中随机值的向量/](https://www.geeksforgeeks.org/how-to-generate-a-vector-with-random-values-in-c/)

[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)是[动态数组](https://www.geeksforgeeks.org/how-do-dynamic-arrays-work/)，能够在插入或删除元素时自动调整自身大小，其存储由[容器](https://www.geeksforgeeks.org/containers-cpp-stl/)自动处理。也可以使用[生成](https://www.geeksforgeeks.org/stdgenerate-in-c/)功能和[兰德](https://www.geeksforgeeks.org/rand-and-srand-in-ccpp/)()功能创建随机值。

下面是两个 **STL** 功能的模板:

**语法:**

> **int rand(void):** 返回一个介于 **0** 到 **RAND_MAX** 之间的伪随机数。
> **RAND_MAX:** 是一个常量，它的默认值可能因实现而异，但它被授权至少为 32767。

> **void generate(ForwardIterator 优先，forward iterator 最后，Generator gen)**

哪里，

*   **首先:**指向容器第一个元素的前向迭代器。
*   **最后:**指向容器最后一个元素的正向迭代器。
*   **gen:** 一个生成器函数，基于该函数将分配值。
*   **返回值:**因为它有一个 void 返回类型，所以不返回值。

为了每次都有不同的随机向量，运行这个程序，思路是使用 **[srand()](https://www.geeksforgeeks.org/rand-and-srand-in-ccpp/)** 功能。否则，每次编译后输出向量将是相同的。

**语法:**

> void srand(无符号种子):这个函数用值 seed 播种 rand()使用的伪随机数生成器。

下面是上述方法的实现:

## C++

```cpp
// C++ program to generate the vector
// with random values
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    // Size of vector
    int size = 5;

    // Initialize the vector with
    // initial values as 0
    vector<int> V(size, 0);

    // use srand() for different outputs
    srand(time(0));

    // Generate value using generate
    // function
    generate(V.begin(), V.end(), rand);

    cout << "The elements of vector are:\n";

    // Print the values in the vector
    for (int i = 0; i < size; i++) {
        cout << V[i] << " ";
    }

    return 0;
}
```

**Output:**

```cpp
The elements of vector are:
995552582 698831766 2088692742 1348138651 64302615

```