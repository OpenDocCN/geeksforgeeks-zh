# std::在 C++ 中查找

> 原文:[https://www.geeksforgeeks.org/std-find-in-cpp/](https://www.geeksforgeeks.org/std-find-in-cpp/)

在给定的数字范围内查找元素。返回范围[第一个，最后一个]中比较等于 val 的第一个元素的迭代器。如果没有找到这样的元素，函数返回 last。

**功能模板:**

> **输入运算符查找(输入运算符第一，输入运算符最后，常量 T &值)**
> 
> **第一个，最后一个:**
> 将迭代器输入到序列的初始和最终位置。搜索的
> 范围是【第一个，最后一个】，包含第一个和
> 最后一个之间的所有元素，包括第一个指向的元素，但不包括最后一个指向的元素。
> 
> **值:**
> 要在范围内搜索的值
> 
> **返回值:**
> 范围内第一个元素的迭代器，比较等于 val。
> 如果没有元素匹配，函数返回最后一个。

**示例:**

```cpp
Input : 10 20 30 40
Output : Element 30 found at position : 2 (counting from zero)  

Input : 8 5 9 2 7 1 3 10
Output : Element 4 not found.    

```

```cpp
// CPP program to illustrate 
// std::find
// CPP program to illustrate 
// std::find
#include<bits/stdc++.h>

int main ()
{
    std::vector<int> vec { 10, 20, 30, 40 };

    // Iterator used to store the position 
    // of searched element
    std::vector<int>::iterator it;

    // Print Original Vector
    std::cout << "Original vector :";
    for (int i=0; i<vec.size(); i++)
        std::cout << " " << vec[i];

    std::cout << "\n";

    // Element to be searched
    int ser = 30;

    // std::find function call
    it = std::find (vec.begin(), vec.end(), ser);
    if (it != vec.end())
    {
        std::cout << "Element " << ser <<" found at position : " ;
        std::cout << it - vec.begin() << " (counting from zero) \n" ;
    }
    else
        std::cout << "Element not found.\n\n";

    return 0;
}
```

输出:

```cpp
Original vector : 10 20 30 40
Element 30 found at position : 2 (counting from zero)

```

**相关文章:**

*   [标准::搜索](https://www.geeksforgeeks.org/stdsearch-in-c/)
*   [std::find_if，std::find_if_not](https://www.geeksforgeeks.org/stdfind_if-stdfind_if_not-in-c/)
*   [标准::第 n _ 元素](https://www.geeksforgeeks.org/stdnth_element-in-cpp/)
*   [std::find_end](https://www.geeksforgeeks.org/stdfind_end-in-cpp/)

本文由**沙钦·毕斯特**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。