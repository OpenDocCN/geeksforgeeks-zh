# c++ 中的信号处理

> 原文:[https://www.geeksforgeeks.org/signal-handling-in-cpp/](https://www.geeksforgeeks.org/signal-handling-in-cpp/)

信号是迫使操作系统停止其正在进行的任务并参与中断已被发送的任务的中断。这些中断可以暂停操作系统中任何程序的服务。类似地，C++ 也提供了它可以在程序中捕捉和处理的各种信号。下面是 C++ 提供给用户使用的各种信号及其操作的列表。

<figure class="table">

| signal | 

操作

 |
| --- | --- |
| SIGINT | Is the activation signal. |
| SIGTERM

 | Send a termination request to the program |
| 西格布斯 | SIGALRM | This is used by the alarm () function to indicate that the timer has expired. |
| SIGABRT | Termination of program, abnormally |
| SIGSTOP | The signal cannot be blocked, processed, ignored and a process can be stopped. |
| SIGSEGV | Invalid access |

</figure>

此 signal()函数由信号库提供，用于捕获意外中断或事件。

**语法:**

```cpp
signal(registered signal, signal handler)
```

第一个参数是整数，表示信号编号，第二个参数是信号处理函数的指针。我们必须记住，我们想要捕捉的信号必须使用信号功能进行注册，并且必须与信号处理功能相关联。信号处理功能应为空型。

**示例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP Program to demonstrate the signal() function
#include <csignal>
#include <iostream>
using namespace std;

void signal_handler(int signal_num)
{
    cout << "The interrupt signal is (" << signal_num
         << "). \n";

    // It terminates the  program
    exit(signal_num);
}

int main()
{
    // register signal SIGABRT and signal handler
    signal(SIGABRT, signal_handler);

    while (true)
        cout << "Hello GeeksforGeeks..." << endl;
    return 0;
}
```

**输出:**在无限循环中，该代码将显示以下输出，直到遇到中断:

```cpp
Hello GeeksforGeeks...
Hello GeeksforGeeks...
Hello GeeksforGeeks...
Hello GeeksforGeeks...
```

现在如果我们按 **Ctrl+C** 发送中断，程序将通过打印退出:

```cpp
Hello GeeksforGeeks...
Hello GeeksforGeeks...
Hello GeeksforGeeks...
Hello GeeksforGeeks...
The interrupt signal is (22).
```

### 提升()功能

raise()函数用于生成信号。

**语法:**

```cpp
raise( signal )
```

它将参数作为列表中提到的任何函数。

**示例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP Program to demonstrate the raise() function
#include <csignal>
#include <iostream>

using namespace std;

void signal_handler(int signal_num)
{
    cout << "Interrupt signal is (" << signal_num << ").\n";

    // It terminates program
    exit(signal_num);
}

int main()
{
    int count = 0;
    signal(SIGSEGV, signal_handler);
    // register signal SIGSEGV and signal handler

    while (++ count) {
        cout << "Hello GeeksforGeeks..." << endl;
        if (count == 5)
            raise(SIGSEGV);
    }
    return 0;
}
```

**Output**

```cpp
Hello GeeksforGeeks...
Hello GeeksforGeeks...
Hello GeeksforGeeks...
Hello GeeksforGeeks...
Hello GeeksforGeeks...
Interrupt signal is (11).
```

本文由 [**【钦莫伊蕾恩卡】**](https://auth.geeksforgeeks.org/profile.php?user=lenkachinmoy) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。