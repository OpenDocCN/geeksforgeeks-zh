# 在 fork()中搜索

> 原文:[https://www.geeksforgeeks.org/searching-in-fork/](https://www.geeksforgeeks.org/searching-in-fork/)

**先决条件–**[fork()in C](https://www.geeksforgeeks.org/fork-system-call/)、 [sorting in fork()](https://www.geeksforgeeks.org/sorting-in-fork/)
**问题语句**–编写程序搜索父进程中的关键元素，打印子进程中需要搜索的关键。

**示例–**

```cpp
Input :
Key = 10;
array[5] = {3, 8, 4, 10, 80};

Output: 
Parent process 
key is  present in array
Child process 
numbers to be search is 10

```

**解释**–这里，我们使用了 [fork( )](https://www.geeksforgeeks.org/fork-system-call/) 函数来创建两个进程一个子进程和一个父进程。

*   fork()为父进程返回大于 0 的值，因此我们可以执行[搜索](https://www.geeksforgeeks.org/binary-search/)操作。
*   对于子进程，fork()返回 0，这样我们就可以打印要搜索的键值。
*   这里我们使用一个简单的搜索算法来搜索给定数组中的关键元素。
*   我们使用 fork()的返回值来知道哪个进程是子进程，哪个是父进程。

**注意–**在某个时刻，子进程不必首先执行，父进程也不必首先分配 CPU，任何进程都可以在某个时间段分配 CPU。此外，在不同的执行过程中，进程 id 可能不同。

**代码–**

```cpp
// C++ program to demonstrate searching
// in parent and printing result
// in child processes using fork()
#include <iostream>
#include <unistd.h>
using namespace std;

// Driver code
int main()
{

    int key = 10;
    int id = fork();

    // Checking value of process id returned by fork
    if (id > 0)  {

        cout << "Parent process \n";

        int a[] = { 3, 8, 4, 10, 80 };
        int n = 5;
        int flag;
        int i;

        for (i = 0; i < n; i++)
        {

            if (a[i] != key) {
                flag = 0;
            }

            else  {

                flag = 1;
            }
        }

        if (flag == 1) {

            cout << "key is not present in array";
        }

        else {

            cout << "key is present in array";
            cout << "\n";

        }
    }

    // If n is 0 i.e. we are in child process
    else {

        cout << "Child process \n";
        cout << "numbers to be search is ";
        cout << key;
    }

    return 0;
}
```

**输出–**

```cpp
Parent process 
key is  present in array
Child process 
numbers to be search is 10

```

本文由 **Pushpanjali Chauhan** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。