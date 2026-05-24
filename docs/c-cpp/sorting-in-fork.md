# 在货叉()中分拣

> 原文:[https://www.geeksforgeeks.org/sorting-in-fork/](https://www.geeksforgeeks.org/sorting-in-fork/)

**先决条件–**[引入 fork()](https://www.geeksforgeeks.org/fork-system-call/) 、[排序算法](https://www.geeksforgeeks.org/sorting-algorithms/)
**问题语句–**编写程序对父进程中的编号进行排序，并打印子进程中未排序的编号。例如:

```cpp
Input : 5, 2, 3, 1, 4

Output :
Parent process 
sorted numbers are
1, 2, 3, 4, 5

Child process 
numbers to sort are
 5, 2, 3, 1, 4

```

**解释–**在这里，我们使用了 [fork()](https://www.geeksforgeeks.org/fork-system-call/) 函数来创建两个进程一个子进程和一个父进程。

*   fork()为父进程返回大于 0 的值，以便我们可以执行排序操作。
*   对于子进程，fork()返回 0，这样我们就可以执行打印操作。
*   这里我们使用一个简单的[排序](https://www.geeksforgeeks.org/sorting-algorithms/)算法来按照期望的顺序对数字进行排序。
*   我们使用 fork()的返回值来知道哪个进程是子进程，哪个是父进程。

**注意–**在某个时刻，子进程不必首先执行，父进程也不必首先分配 CPU，任何进程都可以在某个时间段分配 CPU。此外，在不同的执行过程中，进程 id 可能不同。

**代码–**

```cpp
// C++ program to demonstrate sorting in parent and
// printing result in child processes using fork()
#include <iostream>
#include <unistd.h>
#include <algorithm>
using namespace std;

// Driver code
int main()
{
    int a[] = { 1, 6, 3, 4, 9, 2, 7, 5, 8, 10 };
    int n = sizeof(a)/sizeof(a[0]);
    int id = fork();

    // Checking value of process id returned by fork
    if (id > 0) {
        cout << "Parent process \n";

        sort(a, a+n);

        // Displaying Array
        cout << " sorted numbers are ";
        for (int i = 0; i < n; i++) 
            cout << "\t" << a[i];

        cout << "\n";

    }

    // If n is 0 i.e. we are in child process
    else {
        cout << "Child process \n";
        cout << "\n  numbers to be sorted are ";
        for (int i = 0; i < n; i++) 
            cout << "\t" << a[i];       
    }

    return 0;
}
```

**输出–**

```cpp
Output :
Parent process 
sorted numbers are 1 2 3 4 5 6 7 8 9 10

Child process 
numbers to be sorted are 1 6 3 4 9 2 7 5 8 10

```

本文由 **Pushpanjali Chauhan** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。