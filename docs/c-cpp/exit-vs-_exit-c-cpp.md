# 退出()vs _ 退出()在 C 和 C++ 中

> 原文:[https://www.geeksforgeeks.org/exit-vs-_exit-c-cpp/](https://www.geeksforgeeks.org/exit-vs-_exit-c-cpp/)

在 C 语言中， [exit()](https://www.geeksforgeeks.org/understanding-exit-abort-and-assert/) 终止调用过程，而不执行 exit()函数之后的剩余代码。

示例:-

```cpp
// C program to illustrate exit() function.
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
    printf("START");

    exit(0); // The program is terminated here

    // This line is not printed
    printf("End of program");
}
```

输出:

```cpp
START

```

现在的问题是，如果我们有 exit()函数，那么为什么 C11 标准引入了 _Exit()？实际上 exit()函数在程序终止之前执行一些清理，比如连接终止、缓冲区刷新等。C/C++ 中的 _Exit()函数给出程序的正常终止，而不执行任何清理任务。例如，它不执行用 atexit 注册的函数。

语法:

```cpp
// Here the exit_code represent the exit status 
// of the program which can be 0 or non-zero.
// The _Exit() function returns nothing.
void _Exit(int exit_code);

```

```cpp
// C++ program to demonstrate use of _Exit()
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
    int exit_code = 10;
    printf("Termination using _Exit");
    _Exit(exit_code);

}
```

输出:

**通过节目展示差异:**

```cpp
// A C++ program to show difference
// between exit() and _Exit()
#include<bits/stdc++.h>
using namespace std;

void fun(void)
{
   cout << "Exiting";
}

int main()
{
   atexit(fun);
   exit(10);
}
```

输出

```cpp
Exiting
```

如果我们将 exit 替换为 _Exit()，则不会打印任何内容。

```cpp
// A C++ program to show difference
// between exit() and _Exit()
#include<bits/stdc++.h>
using namespace std;

void fun(void)
{
   cout << "Exiting";
}

int main()
{
   atexit(fun);
   _Exit(10);
}
```

输出

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。