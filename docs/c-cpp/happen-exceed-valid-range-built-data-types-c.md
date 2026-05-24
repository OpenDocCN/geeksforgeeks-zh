# 当我们超过 C++ 中内置数据类型的有效范围时会发生什么？

> 原文:[https://www . geeksforgeeks . org/发生-超出有效范围-构建-数据类型-c/](https://www.geeksforgeeks.org/happen-exceed-valid-range-built-data-types-c/)

考虑以下程序。
1)程序显示当我们穿越“字符”范围时会发生什么:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// the problem with 'char'
#include <iostream>

using namespace std;

int main()
{
    for (char a = 0; a <= 225; a++)
        cout << a;
    return 0;
}
```

被声明为 char。这里的循环是从 0 到 225。所以，它应该从 0 到 225 打印，然后停止。但它会产生一个无限循环。原因是字符数据类型的有效范围是-128 到 127。当“a”通过 a++ 变成 128 时，范围被超过，结果范围负端的第一个数字(即-128)被分配给 a。结果“a”将永远不会到达点 225。所以它会打印出无限系列的字符。
2)程序显示当我们越过‘bool’范围时会发生什么:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// the problem with 'bool'
#include <iostream>

using namespace std;

int main()
{
    // declaring Boolean
    // variable with true value
    bool a = true;

    for (a = 1; a <= 5; a++)
        cout << a;

    return 0;
}
```

此代码将无限次打印“1”，因为这里“a”被声明为“bool”，其有效范围为 0 到 1。对于一个布尔变量，除了 0 之外的任何值都是 1(或真)。当“a”试图变成 2(通过 a++)时，1 被分配给“a”。条件 a <=5 is satisfied and the control remains with in the loop. See [此](https://www.geeksforgeeks.org/bool-data-type-in-c/)为布尔数据类型。
3)程序显示当我们跨越“短”的范围时会发生什么:
注意，short 是 short int 的缩写。他们是同义词。short、short int、带符号 short 和带符号 short int 都是相同的数据类型。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// the problem with 'short'
#include <iostream>

using namespace std;

int main()
{
    // declaring short variable
    short a;

    for (a = 32767; a < 32770; a++)
        cout << a << "\n";

    return 0;
}
```

这个代码会打印“a”直到变成 32770 吗？答案是不定循环，因为这里‘a’被声明为一个短，它的有效范围是-32768 到+32767。当“a”试图通过 a++ 变成 32768 时，范围被超过，结果范围负端的第一个数字(即-32768)被分配给 a。因此条件“a < 32770” is satisfied and control remains within the loop.
4)程序显示当我们跨越“无符号短:”的范围时会发生什么

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// the problem with 'unsigned short'
#include <iostream>

using namespace std;

int main()
{
    unsigned short a;

    for (a = 65532; a < 65536; a++)
        cout << a << "\n";

    return 0;
}
```

这个代码会打印“a”直到变成 65536 吗？答案是不定循环，因为这里‘a’被声明为一个短，它的有效范围是 0 到+65535。当‘a’试图通过 a++ 变成 65536 时，范围被超过，结果范围中的第一个数字(即 0)被分配给 a。因此条件“a < 65536” is satisfied and control remains within the loop.
**解释–**
我们知道计算机使用 2 的补码来表示数据。例如，如果我们有 1 个字节(我们可以使用 char 并使用%d 作为格式说明符来将其视为十进制)，我们可以表示-128 到 127。如果我们把 1 加到 127，我们将得到-128。那是因为 127 在二进制中是 01111111。如果我们在 01111111 中加上 1，我们将得到 10000000。10000000 是 2 补码形式的-128。
如果我们使用无符号整数，也会发生同样的情况。255 是 1111111111 当我们把 1 加到 111111111 上时，我们会得到 100000000。但是我们只使用前 8 位，所以是 0。因此我们在 255 中加 1 后得到 0。
本文由 [**Aditya Rakhecha**](https://www.linkedin.com/in/aditya-rakhecha-34a597129/) 投稿，经 **Sakshi Tiwari** 改进，如果你喜欢 GeeksforGeeks 并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。