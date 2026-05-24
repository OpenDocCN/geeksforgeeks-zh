# C/c++

中的系统()

> 原文:[https://www.geeksforgeeks.org/system-call-in-c/](https://www.geeksforgeeks.org/system-call-in-c/)

system()用于从 C/C++ 程序中调用操作系统命令。

```cpp
    int system(const char *command);

```

**注意:**需要包含 stdlib.h 或 cstdlib 才能调用系统。

使用 system()，如果操作系统允许，我们可以执行任何可以在终端上运行的命令。例如，我们可以在 Windows 上调用 system(“dir”)和 system(“ls”)来列出目录的内容。

**编写 C/C++ 程序，编译运行其他程序？**
我们可以使用系统()从程序中调用 gcc。请参见下面为 Linux 编写的代码。我们可以轻松地将代码更改为在 windows 上运行。

```cpp
// A C++ program that compiles and runs another C++ 
// program
#include <bits/stdc++.h>
using namespace std;
int main ()
{
    char filename[100];
    cout << "Enter file name to compile ";
    cin.getline(filename, 100);

    // Build command to execute.  For example if the input
    // file name is a.cpp, then str holds "gcc -o a.out a.cpp" 
    // Here -o is used to specify executable file name
    string str = "gcc ";
    str = str + " -o a.out " + filename;

    // Convert string to const char * as system requires
    // parameter of type const char *
    const char *command = str.c_str();

    cout << "Compiling file using " << command << endl;
    system(command);

    cout << "\nRunning file ";
    system("./a.out");

    return 0;
}
```

**system() vs 使用库函数:**
system()在 Windows OS 中的一些常见用法是，system(“pause”)用于执行暂停命令，使屏幕/终端等待按键，system(“cls”)用于使屏幕/终端清晰。

但是，由于以下原因，应避免调用系统命令:

1.  **<u>这是一个非常昂贵且资源繁重的功能调用</u>**
2.  **<u>不可移植</u>** :使用 system()使程序非常不可移植，也就是说这只能在系统级有暂停命令的系统上工作，比如 DOS 或者 Windows。但不是 Linux、MAC OSX 和大多数其他系统。

让我们用一个简单的 C++ 代码，用**系统(“暂停”)**输出 Hello World:

```cpp
// A C++ program that pauses screen at the end in Windows OS
#include <iostream>
using namespace std;
int main ()
{
    cout << "Hello World!" << endl;
    system("pause");
    return 0;
}
```

以上程序在 Windows 操作系统中的输出:

```cpp
Hello World!
Press any key to continue…
```

该程序依赖于操作系统，使用以下沉重的步骤。

*   它会挂起您的程序，同时调用操作系统来打开操作系统外壳。
*   操作系统发现暂停并分配内存来执行命令。
*   然后，它释放内存，退出操作系统并恢复程序。

除了使用系统(“暂停”)，我们还可以使用在 C/C++ 中本地定义的函数。

让我们举一个简单的例子，用 cin.get()输出 Hello World:

```cpp
// Replacing system() with library function
#include <iostream>
#include <cstdlib>
using namespace std;
int main ()
{
    cout << "Hello World!" << endl;
    cin.get();  // or getchar()
    return 0;
}
```

程序的输出是:

```cpp
 Hello World!
```

因此，我们看到**系统(“暂停”)**和 **cin.get()** 实际上都在等待一个键被按下，但是 cin.get()不依赖于操作系统，也不遵循上述步骤来暂停程序。
同样，在 C 语言中，可以使用 **getchar()** 暂停程序，而不打印消息“按任意键继续……”。

**检查我们是否可以在操作系统中使用 system()运行命令的常用方法？**
如果我们传递空指针代替命令参数的字符串，如果命令处理器存在(或者系统可以运行)，系统返回非零值。否则返回 0。

```cpp
// C++ program to check if we can run commands using 
// system()
#include <iostream>
#include <cstdlib>
using namespace std;
int main ()
{
    if (system(NULL))
       cout << "Command processor exists";
    else
       cout << "Command processor doesn't exists";

    return 0;
}
```

请注意，上述程序可能无法在在线编译器上运行，因为大多数在线编译器都禁用了 System 命令，包括 [GeeksforGeeks IDE](https://ide.geeksforgeeks.org/) 。

本文由 **Subhankar Das 供稿。**如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。