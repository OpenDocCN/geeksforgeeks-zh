# 在竞争性编程中高效编写 C/C++ 代码

> 原文:[https://www . geesforgeks . org/writing-cc-code-in-competitive-programming/](https://www.geeksforgeeks.org/writing-cc-code-efficiently-in-competitive-programming/)

首先你需要了解[模板](https://www.geeksforgeeks.org/template-specialization-c/)、[宏](https://www.geeksforgeeks.org/interesting-facts-preprocessors-c/)和[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)才能进入下一阶段！

*   模板是泛型编程的基础，泛型编程涉及以独立于任何特定类型的方式编写代码。
*   宏是一段已被命名的代码。每当使用该名称时，它都会被宏的内容替换。
*   向量与动态数组相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。

因此，我们可以使用这些强大的工具以有效的方式编写代码。
竞技编程中可能用到的一些很酷的技巧如下:

*   **使用基于范围的循环**:这是 C++ 11 中非常酷的特性，如果你想从头到尾迭代，这将被认为是最好的。这段代码展示了如何使用 ranged for 循环迭代数组和向量:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate range based for
// loops for accessing vector and array elements
#include<iostream>
#include <vector>
using namespace std;

int main()
{
    // Create a vector object that
    // contains 5 elements
    vector<int> vec = {0, 1, 2, 3, 4};

    // Type inference by reference using auto.
    // Range based loops are preferred when no
    // modification is needed in value
    for (const auto &value : vec)
        cout << value << ' ';

    cout << '\n';

    // Basic 5 element integer array
    int array[]= {1, 2, 3, 4, 5};
    for (const auto &value: array)
        cout << value << " ";

    return 0;
}
```

**输出:**

```cpp
0 1 2 3 4
1 2 3 4 5
```

*   **初始化列表:**该类型用于访问 C++ 初始化列表中的值。这里，这种类型的对象是由编译器根据初始化列表声明自动构造的，初始化列表声明是用大括号括起来的逗号分隔的元素列表。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>

template<typename T>
void printList(std::initializer_list<T> text)
{
    for (const auto & value: text)
        std::cout << value << " ";
}

// Driver program
int main()
{
    // Initialization list
    printList( {"One", "Two", "Three"} );
    return 0;
}
```

**输出:**

```cpp
One Two Three
```

*   **分配最大值或最小值:**这个值对于避免编写 max()或 min()函数的额外工作很有用。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>

// Call by reference is used in x
template<typename T, typename U>
static inline void amin(T &x, U y)
{
    if (y < x)
        x = y;
}

// call by reference is used in x
template<typename T, typename U>
static inline void amax(T &x, U y)
{
    if (x < y)
        x = y;
}

// Driver program to find the Maximum and Minimum value
int main()
{
    int max_val = 0, min_val = 1e5;
    int array[]= {4, -5, 6, -9, 2, 11};

    for (auto const &val: array)

        // Same as max_val = max (max_val, val)
        // Same as min_val = min (min_val,val)
        amax(max_val, val), amin (min_val, val);

    std::cout << "Max value = " << max_val << "\n"
              << "Min value = " << min_val;
    return 0;
}
```

**输出:**

```cpp
Max value = 11
Min value = -9
```

*   **C/c++ 中的快速输入/输出:**在竞争性编程中，必须尽可能快地读取输入/输出，以节省宝贵的时间。

## C

```cpp
#include <bits/stdc++.h>

template<typename T> void scan(T &x)
{
    x = 0;
    bool neg = 0;
    register T c = getchar();

    if (c == '-')
        neg = 1, c = getchar();

    while ((c < 48) || (c > 57))
        c = getchar();

    for ( ; c < 48||c > 57 ; c = getchar());

    for ( ; c > 47 && c < 58; c = getchar() )
        x= (x << 3) + ( x << 1 ) + ( c & 15 );

    if (neg) x *= -1;
}

template<typename T> void print(T n)
{
    bool neg = 0;

    if (n < 0)
        n *= -1, neg = 1;

    char snum[65];
    int i = 0;
    do
    {
        snum[i++ ] = n % 10 + '0';
        n /= 10;
    }

    while (n);
    --i;

    if (neg)
        putchar('-');

    while (i >= 0)
        putchar(snum[i--]);

    putchar('\n');
}

// Driver Program
int main()
{
    int value;

    // Taking input
    scan(value);

    // Printing output
    print(value);
    return 0;
}
```

```cpp
Input:  756
Output: 756
```

想了解更多关于快速输入输出的知识[阅读这篇文章](https://www.geeksforgeeks.org/fast-io-for-competitive-programming/)。

*   **使用宏作为循环**:也许使用这样的宏并不好，因为会降低代码的可读性，但是为了编写快速的代码，你可以冒这个险！

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <bits/stdc++.h>
using namespace std;

#define rep(i,n) for (i = 0; i < n; ++ i)
#define REP(i,k,n) for (i = k; i <= n; ++ i)
#define REPR(i,k,n) for (i = k; i >= n; --i)

// Driver program to test above Macros
int main()
{
    int i;
    int array[] = {4, 5, 6, 9, 22, 11};
    int size= sizeof(array)/sizeof(array[0]);

    // Default 0 index based loop
    rep(i, size)    
        cout << array[i] << " ";
    cout<<"\n";

    // Starting index based loop
    REP(i, 1, size-1)    
        cout << array[i] << " ";
    cout<<"\n";

    // Reverse for loop
    REPR(i, size-1,0)    
        cout << array[i] << " ";
    return 0;
}
```

**输出**

```cpp
4 5 6 9 22 11
5 6 9 22 11
11 22 9 6 5 4
```

*   **使用“bit/stdc++”。h":** 不用增加成吨的#include 行，直接用#include <位/stdc++。h >文件包括了你在竞技编程中需要的所有头文件，节省了你很多时间。
*   **容器:**使用各种容器，如向量、列表、映射等，可以使用预定义的函数，并大大减少代码的大小(通常情况下)
*   **快速 cin 和 cout:** 如果使用 cin 和 cout 进行 I/O，只需在 main()之后添加以下行即可。

```cpp
std::ios_base::sync_with_stdio(false);
```

*   **auto:** 使用 auto 声明数据类型可以在编程竞赛中节省大量时间。当变量被定义为 auto 时，编译器在编译时确定其类型。
*   **库和预定义函数:**使用内置函数，如 __gcd(A，B)，交换，_builtin_popcount(R)，_builtin_clz(R)等，只要可以应用。尝试学习 C++ 的[算法](https://www.geeksforgeeks.org/c-magicians-stl-algorithms/)库中可用的不同函数。它们在程序中大多数时候都是有用的

最终，通过使用这些聪明的技巧，你可以用最少的时间和单词轻松地编写代码。
本文由[舒巴姆·班萨尔](https://www.facebook.com/banalshubham)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。