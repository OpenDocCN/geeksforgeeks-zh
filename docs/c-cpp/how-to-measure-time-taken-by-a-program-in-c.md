# 如何测量一个函数在 C 中花费的时间？

> 原文:[https://www . geesforgeks . org/如何测量 c 中程序花费的时间/](https://www.geeksforgeeks.org/how-to-measure-time-taken-by-a-program-in-c/)

要计算一个进程所花费的时间，我们可以使用 *time.h* 提供的 [clock()](http://www.gnu.org/software/libc/manual/html_node/CPU-Time.html) 功能。我们可以在我们测量时间的代码的开头和结尾调用 clock 函数，减去这些值，然后除以 [CLOCKS_PER_SEC](http://www.cplusplus.com/reference/ctime/CLOCKS_PER_SEC/) (每秒钟的时钟节拍数)得到处理器时间，如下所示。

```cpp
     #include <time.h>

     clock_t start, end;
     double cpu_time_used;

     start = clock();
     ... /* Do the work. */
     end = clock();
     cpu_time_used = ((double) (end - start)) / CLOCKS_PER_SEC;

```

下面是一个示例 C 程序，我们在其中测量乐趣所花费的时间()。fun()函数等待回车键按下终止。

```cpp
/* Program to demonstrate time taken by function fun() */
#include <stdio.h>
#include <time.h>

// A function that terminates when enter key is pressed
void fun()
{
    printf("fun() starts \n");
    printf("Press enter to stop fun \n");
    while(1)
    {
        if (getchar())
            break;
    }
    printf("fun() ends \n");
}

// The main program calls fun() and measures time taken by fun()
int main()
{
    // Calculate the time taken by fun()
    clock_t t;
    t = clock();
    fun();
    t = clock() - t;
    double time_taken = ((double)t)/CLOCKS_PER_SEC; // in seconds

    printf("fun() took %f seconds to execute \n", time_taken);
    return 0;
}
```

输出:等待 4 秒左右，然后按回车键，得到如下输出。

```cpp
fun() starts
Press enter to stop fun

fun() ends
fun() took 4.017000 seconds to execute

```

[如何在 Linux Shell 上查找一个命令/程序所花费的时间？](https://www.geeksforgeeks.org/how-to-find-time-taken-by-a-program-on-linux-shell/)

**参考文献:**
[http://www . GNU . org/software/libc/manual/html _ node/CPU-time . html](http://www.gnu.org/software/libc/manual/html_node/CPU-Time.html)
[http://www.cplusplus.com/reference/ctime/clock/?kw=clock](http://www.cplusplus.com/reference/ctime/clock/?kw=clock)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。