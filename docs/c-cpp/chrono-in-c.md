# c++ 中的 Chrono

> 原文:[https://www.geeksforgeeks.org/chrono-in-c/](https://www.geeksforgeeks.org/chrono-in-c/)

Chrono 库用于处理日期和时间。该库旨在处理不同系统上计时器和时钟可能不同的事实，从而随着时间的推移提高精度。chrono 的独特之处在于，它通过将持续时间和时间点(“时间点”)与特定时钟分开，提供了一个**精度中性的概念。**

chrono 是一个头的名称，也是一个子命名空间的名称:这个头中的所有元素(除了 common_type 专门化)不是直接在 std 命名空间下定义的(像大多数标准库一样)，而是在 **std::chrono 命名空间**下定义的。
这个标题中的元素与时间有关。这主要通过三个概念来实现:

**持续时间**

持续时间对象通过一分钟、两小时或十毫秒这样的计数来表示时间跨度。例如，“42 秒”可以由 1 秒时间单位的 42 个刻度组成的持续时间来表示。

```cpp
// C++ program to illustrate the utility 
// function duration::count
#include <iostream> 
#include <chrono>    

int main ()
{
    using namespace std::chrono;
    // std::chrono::milliseconds is an 
    // instantiation of std::chrono::duration:- 1 second
    milliseconds mil(1000); 

    mil = mil*60;

    std::cout << "duration (in periods): ";
    std::cout << mil.count() << " milliseconds.\n";

    std::cout << "duration (in seconds): ";
    std::cout << (mil.count() * milliseconds::period::num / 
                               milliseconds::period::den);
    std::cout << " seconds.\n";

    return 0;
}
```

输出:

```cpp
duration (in periods): 60000 milliseconds.
duration (in seconds): 60 seconds.

```

**时钟**

时钟由一个起点(或纪元)和一个刻度率组成。例如，一个时钟可能有一个 1996 年 2 月 22 日的纪元，并且每秒都在滴答作响。C++ 定义了三种时钟类型:

*   **system _ clock**-是根据系统显示的当前时间(我们在电脑工具栏上看到的常规时钟)。它被写成- std::chrono::system_clock

*   **stable _ clock**-是一个永不调整的单调时钟。它以统一的速度前进。它被写成-STD::chrono::stable _ clock

*   **高分辨率时钟**–它提供尽可能小的滴答周期。它被写成-STD::chrono::high _ resolution _ clock

**时间点**

time_point 对象表示相对于时钟周期的时间点。在内部，对象存储持续时间类型的对象，并使用时钟类型作为其纪元的参考。

```cpp
// C++ program to illustrate time point
// and system clock functions
#include <iostream>
#include <chrono>
#include <ctime>

// Function to calculate
// Fibonacci series
long fibonacci(unsigned n)
{
    if (n < 2) return n;
    return fibonacci(n-1) + fibonacci(n-2);
}

int main()
{
    // Using time point and system_clock
    std::chrono::time_point<std::chrono::system_clock> start, end;

    start = std::chrono::system_clock::now();
    std::cout << "f(42) = " << fibonacci(42) << '\n';
    end = std::chrono::system_clock::now();

    std::chrono::duration<double> elapsed_seconds = end - start;
    std::time_t end_time = std::chrono::system_clock::to_time_t(end);

    std::cout << "finished computation at " << std::ctime(&end_time)
              << "elapsed time: " << elapsed_seconds.count() << "s\n";
}
```

输出:

```cpp
f(42) = 267914296
finished computation at Wed Jan  4 05:13:48 2017
elapsed time: 2.14538s

```

本文由**香巴拉维·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。