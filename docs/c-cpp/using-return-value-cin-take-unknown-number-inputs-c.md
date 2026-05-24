# 用 cin 的返回值在 C++ 中取未知数量的输入

> 原文:[https://www . geesforgeks . org/using-return-value-CIN-take-unknown-number-inputs-c/](https://www.geeksforgeeks.org/using-return-value-cin-take-unknown-number-inputs-c/)

考虑一个问题，其中我们需要接受未知数量的整数输入。

典型的解决方案是运行一个循环，并在用户输入特定值时停止。如果不允许我们使用 if-else、switch-case 和条件语句，该怎么做呢？

其思想是使用这样一个事实，即如果给定非数值，“cin > >输入”为假。请注意，只有当输入值的数据类型为 int(整数)时，上述方法才成立。

要点:cin 是性病的对象。在 C++ 11 及更高版本中，std::istream 有一个转换函数 explicit bool()const；，这意味着从 std::istream 到 bool 存在有效的转换，但仅在明确请求的情况下。if 或 while 算作显式请求转换为 bool。【来源 [StackOVerflow](https://stackoverflow.com/questions/40896106/address-and-return-values-of-cin)

在 C++ 11 之前，std::istream 有到运算符 void *(const)的转换；

## C++

```cpp
// C++ program to take unknown number
// of integers from user.
#include <iostream>
using namespace std;
int main()
{
    int input;
    int count = 0;
    cout << "To stop enter any character";
    cout << "\nEnter Your Input::";

    // cin returns false when a character
    // is entered
    while (cin >> input)
        count++ ;

    cout << "\nTotal number of inputs entered: "
         << count;
    return 0;
}
```

输出:

```cpp
To stop enter any character
Enter Your Input 1 2 3 s
Total number of inputs entered: 3
```

本文由 [**阿迪蒂亚·拉赫查**](https://www.linkedin.com/in/aditya-rakhecha-34a597129/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。