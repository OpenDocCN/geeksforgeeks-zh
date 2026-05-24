# 用 C/C++ 打印 2D 矩阵不同行，不带花括号？

> 原文:[https://www . geeksforgeeks . org/print-2d-不同行中的矩阵和不带花括号的 cc/](https://www.geeksforgeeks.org/print-2d-matrix-in-different-lines-and-without-curly-braces-in-cc/)

以下是打印 2D 矩阵的一般方法，即每行都以单独的行打印。

```cpp
for (int i = 0; i < m; i++)
{
   for (int j = 0; j < n; j++)
   {
      cout << arr[i][j] << " ";
   }

   // Newline for new row
   cout << endl;
}
```

**如何在 for 循环中不使用任何花括号的情况下打印打印？**

**我们强烈建议你尽量减少浏览器，先自己试试这个。**

我们可以简单地删除内部花括号，因为有一个单行的内部 for 循环。如何去掉外花括号？下面是解决方案。

```cpp
// C++ program to print a matrix line by line without
// using curly braces.
#include<iostream>
using namespace std;

int main()
{
    int m = 2, n = 3; 
    int mat[][3] = { {1, 2, 3},
                    {4, 5, 6},
                  };
    for (int i = 0; i < m; i++)
       for (int j = 0; j < n; j++)

          // Prints ' ' if j != n-1 else prints '\n'          
          cout << mat[i][j] << " \n"[j == n-1];

    return 0;
}
```

输出:

```cpp
1 2 3
4 5 6
```

实际诀窍在下面的语句 **"\n"[j == n-1]** ，解释如下:

“\n”是一个 2 个字符的字符串，其中 1 <sup>st</sup> 字符是空格，2 <sup>nd</sup> 字符是换行符，所以我们希望每个值后面都有空格，除了最后一个值，我们希望它有一个换行符。在 C 语言中，字符串被视为字符数组[更多细节请参见[这一章](http://c-faq.com/decl/strlitinit.html)]。

对于内部元素，j == n-1 语句的计算结果为 0(因为对于它们，j < n-1)，对于(每行的)最后一个值，它变成 1。因此，对于内部元素，语句的计算结果为“\n”[0]即“0”，对于每行的最后一个元素“\ n”[1]即“\ n”如果您发现任何不正确的地方，或者您想分享有关上述主题的更多信息，请写下注释。