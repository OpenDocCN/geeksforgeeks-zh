# c++ 中基于范围的循环

> 原文:[https://www.geeksforgeeks.org/range-based-loop-c/](https://www.geeksforgeeks.org/range-based-loop-c/)

C++ 中基于范围的 for 循环是从 C++ 11 开始添加的。它在一个范围内执行 for 循环。用作对一系列值(如容器中的所有元素)进行操作的传统 for 循环的更具可读性的等价物。

**语法:**

```cpp
for ( range_declaration : range_expression ) 
    loop_statement

Parameters :
range_declaration : 
a declaration of a named variable, whose type is the 
type of the element of the sequence represented by 
range_expression, or a reference to that type.
Often uses the auto specifier for automatic type 
deduction.

range_expression : 
any expression that represents a suitable sequence 
or a braced-init-list.

loop_statement : 
any statement, typically a compound statement, which
is the body of the loop.

```

C++ 实现:

```cpp
// Illustration of range-for loop
// using CPP code
#include <iostream>
#include <vector>
#include <map>

//Driver
int main() 
{
    // Iterating over whole array
    std::vector<int> v = {0, 1, 2, 3, 4, 5};
    for (auto i : v)
        std::cout << i << ' ';

    std::cout << '\n';

    // the initializer may be a braced-init-list
    for (int n : {0, 1, 2, 3, 4, 5})
        std::cout << n << ' ';

    std::cout << '\n';

    // Iterating over array
    int a[] = {0, 1, 2, 3, 4, 5};     
    for (int n : a)
        std::cout << n << ' ';

    std::cout << '\n';

    // Just running a loop for every array
    // element
    for (int n : a)  
        std::cout << "In loop" << ' ';

    std::cout << '\n';

    // Printing string characters
    std::string str = "Geeks";
    for (char c : str) 
        std::cout << c << ' ';

    std::cout << '\n';

    // Printing keys and values of a map
    std::map <int, int> MAP({{1, 1}, {2, 2}, {3, 3}});
    for (auto i : MAP)
        std::cout << '{' << i.first << ", " 
                  << i.second << "}\n";
}
```

输出:

```cpp
0 1 2 3 4 5 
0 1 2 3 4 5 
0 1 2 3 4 5 
In loop In loop In loop In loop In loop In loop 
G e e k s 
{1, 1}
{2, 2}
{3, 3}

```

本文由 **[罗希特·塔普利亚尔](https://www.hackerrank.com/rohit_thapliyal)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。