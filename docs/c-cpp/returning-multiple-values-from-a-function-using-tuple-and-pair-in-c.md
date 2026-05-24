# std::tuple，std::pair |在 C++ 中使用 tuple 和 pair 从函数返回多个值

> 原文:[https://www . geeksforgeeks . org/使用 c 中的元组和对从函数返回多个值/](https://www.geeksforgeeks.org/returning-multiple-values-from-a-function-using-tuple-and-pair-in-c/)

在某些情况下，您需要在解决问题时返回多个值(可能是不同的数据类型)。一种方法是使用指针、结构或全局变量，这里已经讨论过了
还有一种有趣的方法不用上述方法也可以这样做，使用元组(用于返回多个值)和对(用于两个值)。

我们可以将返回类型声明为 pair 或 tuple(无论哪一个是必需的)的函数，并且可以打包要返回的值并返回打包的值集。返回值可以在调用函数中解包。

**元组**

*   元组是能够保存元素集合的对象，其中每个元素可以是不同的类型。
*   类模板`std::tuple`是一个固定大小的异构值集合

**配对**

*   这个类将一对可能属于不同类型的值连接在一起
*   一对是具有两个元素的 std::tuple 的特定情况

*注意:Tuple 也可以用来返回两个值，而不是使用 pair。*

```cpp
#include<bits/stdc++.h>
using namespace std;

// A Method that returns multiple values using
// tuple in C++.
tuple<int, int, char> foo(int n1, int n2)
{
    // Packing values to return a tuple
    return make_tuple(n2, n1, 'a');             
}

// A Method returns a pair of values using pair
std::pair<int, int> foo1(int num1, int num2)
{
    // Packing two values to return a pair 
    return std::make_pair(num2, num1);            
}

int main()
{
    int a,b;
    char cc;

    // Unpack the elements returned by foo
    tie(a, b, cc) = foo(5, 10);      

    // Storing  returned values in a pair 
    pair<int, int> p = foo1(5,2);  

    cout << "Values returned by tuple: ";
    cout << a << " " << b << " " << cc << endl;

    cout << "Values returned by Pair: ";
    cout << p.first << " " << p.second;
    return 0;
}
```

输出:

```cpp
Values returned by tuple: 10 5 a
Values returned by Pair: 2 5

```

本文由 **Mayank Rawat 供稿。**如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论