# 在父进程和子进程中使用 fork()进行计算

> 原文:[https://www . geeksforgeeks . org/calculation-parent-child-process-using-fork/](https://www.geeksforgeeks.org/calculation-parent-child-process-using-fork/)

写一个程序，求父进程的偶数和，子进程的奇数和。

**示例:**

```cpp
Input : 1, 2, 3, 4, 5 

Output :
Parent process 
Sum of even no. is 6
Child process 
Sum of odd no. is 9 
```

**说明:**在这里，我们已经使用 [fork()](https://www.geeksforgeeks.org/fork-system-call/) 函数创建了两个进程一个子进程和一个父进程。

*   对于子进程 fork() **返回 0** 所以我们可以计算子进程中所有奇数的和。
*   fork()为父进程返回大于 0 的值**，这样我们就可以计算总和**
*   **对于所有偶数，只需检查 fork()返回的值。**

## **C++**

```cpp
// C++ program to demonstrate calculation in parent and
// child processes using fork()
#include <iostream>
#include <unistd.h>
using namespace std;

// Driver code
int main()
{
    int a[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
    int sumOdd = 0, sumEven = 0, n, i;
    n = fork();

    // Checking if n is not 0
    if (n > 0) {
        for (i = 0; i < 10; i++) {
            if (a[i] % 2 == 0)
                sumEven = sumEven + a[i];
        }
        cout << "Parent process \n";
        cout << "Sum of even no. is " << sumEven << endl;
    }

    // If n is 0 i.e. we are in child process
    else {
        for (i = 0; i < 10; i++) {
            if (a[i] % 2 != 0)
                sumOdd = sumOdd + a[i];
        }
        cout << "Child process \n";
        cout << "\nSum of odd no. is " << sumOdd << endl;
    }
    return 0;
}
```

****输出:****

```cpp
Parent process 
Sum of even no. is 30
Child process 
Sum of odd no. is 25
```

**本文由 **Pushpanjali Chauhan** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**