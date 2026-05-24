# STD::c++ 中的 inner _ product

> 原文:[https://www.geeksforgeeks.org/std-inner_product-in-cpp/](https://www.geeksforgeeks.org/std-inner_product-in-cpp/)

**计算范围的累计内积**
返回从第一个 1 和第一个 2 开始的两个范围的元素形成的对的内积的累计结果。
两个默认操作(将对相乘的结果相加)可能会被参数 binary_op1 和 binary_op2 覆盖。
1。**使用默认内积:**
语法:

```cpp
Template :
T inner_product (InputIterator1 first1, InputIterator1 last1,
                 InputIterator2 first2, T init);

Parameters :

first1, last1
Input iterators to the initial and final positions in the first
sequence.

first2
Input iterator to the initial position in the second sequence.
The range starts at first2 and has as many elements as the range
above [first1, last1].

init
Initial value for the accumulator.

Neither operations shall modify any of the elements passed as
its arguments.

Return Type :
The result of accumulating init and the products of all the pairs
of elements in the ranges starting at first1 and first2.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// std :: inner_product
#include <iostream> // std::cout
#include <functional> // std::minus, std::divides
#include <numeric> // std::inner_product

// Driver code
int main()
{
    // The value which is added after
    // finding inner_product b/w elements
    int init = 100;
    int series1[] = { 10, 20, 30 };
    int series2[] = { 1, 2, 3 };
    int n = sizeof(series1) / sizeof(series1[0]);

    // Elements in series1
    std::cout << "First array contains :";
    for (int i = 0; i < n; i++)
        std::cout << " " << series1[i];
    std::cout << "\n";

    // Elements in series2
    std::cout << "Second array contains :";
    for (int i = 0; i < n; i++)
        std::cout << " " << series2[i];
    std::cout << "\n\n";

    std::cout << "Using default inner_product: ";
    std::cout << std::inner_product(series1, series1 + n, series2, init);
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
First array contains : 10 20 30
Second array contains : 1 2 3

Using default inner_product: 240
```

2.**使用功能操作:**
语法:

```cpp
Template :
T inner_product (InputIterator1 first1, InputIterator1 last1,
                 InputIterator2 first2, T init,
                 BinaryOperation1 binary_op1,
                 BinaryOperation2 binary_op2);

Parameters :

first1, last1, first2, init are same as above.

binary_op1
Binary operation taking two elements of type T as arguments, and
returning the result of an accumulation operation.
This can either be a function pointer or a function object.

binary_op2
Binary operation taking two elements of type T as arguments, and
returning the result of the inner product operation.
This can either be a function pointer or a function object.

Here binary_op1 and binary_op2 are functional operation.

Neither operations shall modify any of the elements passed as
its arguments.

Return Type :
The result of accumulating init and the products of all the pairs
of elements in the ranges starting at first1 and first2.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// std :: inner_product
#include <iostream> // std::cout
#include <functional> // std::minus, std::divides
#include <numeric> // std::inner_product

// Driver code
int main()
{
    // The value which is added after
    // finding inner_product b/w elements
    int init = 100;
    int series1[] = { 10, 20, 30 };
    int series2[] = { 1, 2, 3 };
    int n = sizeof(series1) / sizeof(series1[0]);

    // Elements in series1
    std::cout << "First array contains :";
    for (int i = 0; i < n; i++)
        std::cout << " " << series1[i];
    std::cout << "\n";

    // Elements in series2
    std::cout << "Second array contains :";
    for (int i = 0; i < n; i++)
        std::cout << " " << series2[i];
    std::cout << "\n\n";

    std::cout << "Using functional operations: ";
    // std :: minus returns the difference b/w
    // each elements of both array
    // std :: divides return the quotient of
    // each elements of both array after performing
    // divide operation
    // The operations is performed b/w number of same index
    // of both array
    std::cout << std::inner_product(series1, series1 + n, series2, init,
                                    std::minus<int>(), std::divides<int>());
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
First array contains : 10 20 30
Second array contains : 1 2 3

Using functional operations: 70
```

3.**使用自定义函数:**
语法:

```cpp
Template :
T inner_product (InputIterator1 first1, InputIterator1 last1,
                 InputIterator2 first2, T init,
                 BinaryOperation1 binary_op1,
                 BinaryOperation2 binary_op2);

Parameters :

first1, last1, first2, init are same as above.

binary_op1
Binary operation taking two elements of type T as arguments, and
returning the result of an accumulation operation.
This can either be a function pointer or a function object.

binary_op2
Binary operation taking two elements of type T as arguments, and
returning the result of the inner product operation.
This can either be a function pointer or a function object.

Neither operations shall modify any of the elements passed as
its arguments.

Return Type :
The result of accumulating init and the products of all the pairs
of elements in the ranges starting at first1 and first2.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// std :: inner_product
#include <iostream> // std::cout
#include <functional> // std::minus, std::divides
#include <numeric> // std::inner_product

// Custom functions
int myaccumulator(int x, int y)
{
    return x - y;
}
int myproduct(int x, int y)
{
    return x + y;
}

// Driver code
int main()
{
    // The value which is added after
    // finding inner_product b/w elements
    int init = 100;
    int series1[] = { 10, 20, 30 };
    int series2[] = { 1, 2, 3 };
    int n = sizeof(series1) / sizeof(series1[0]);

    // Elements in series1
    std::cout << "First array contains :";
    for (int i = 0; i < n; i++)
        std::cout << " " << series1[i];
    std::cout << "\n";

    // Elements in series2
    std::cout << "Second array contains :";
    for (int i = 0; i < n; i++)
        std::cout << " " << series2[i];
    std::cout << "\n\n";

    std::cout << "Using custom functions: ";
    std::cout << std::inner_product(series1, series1 + 3, series2, init,
                                    myaccumulator, myproduct);
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
First array contains : 10 20 30
Second array contains : 1 2 3

Using custom functions: 34
```

**注意:**
通过使用**功能值**和**自定义功能**，我们可以在这个 STL 功能中通过改变操作符(或使用不同的功能值)来进行操作。
**可能的应用:**它返回用从第一个 1 和第一个 2 开始的两个范围的元素形成的对的内积累加 init 的结果。
1。它可以用来求两个数组的第一个索引的乘积之和。
举例:
数组 1 : 1 2 3 4
数组 2 : 10 20 30 40
积之和:300
**说明:**1 * 10+2 * 20+3 * 30+4 * 40 = 300

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// std :: inner_product
#include <iostream> // std::cout
#include <functional> // std::minus, std::divides
#include <numeric> // std::inner_product

// Custom functions
int myaccumulator(int x, int y)
{
    return x + y;
}
int myproduct(int x, int y)
{
    return x * y;
}

// Driver code
int main()
{
    // The value which is added after
    // finding inner_product b/w elements
    int init = 0;
    int series1[] = { 1, 2, 3, 4 };
    int series2[] = { 10, 20, 30, 40 };
    int n = sizeof(series1) / sizeof(series1[0]);

    // Elements in series1
    std::cout << "Array 1 :";
    for (int i = 0; i < n; i++)
        std::cout << " " << series1[i];
    std::cout << "\n";

    // Elements in series2
    std::cout << "Array 2 :";
    for (int i = 0; i < n; i++)
        std::cout << " " << series2[i];
    std::cout << "\n\n";

    std::cout << "Sum of products : ";
    std::cout << std::inner_product(series1, series1 + n, series2, init,
                                    myaccumulator, myproduct);
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
Array 1 : 1 2 3 4
Array 2 : 10 20 30 40

Sum of products : 300
```

我们也可以通过改变算子来找到乘积的差，或者除法的和，或者除法的差等等。
本文由**沙钦·比斯特**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。