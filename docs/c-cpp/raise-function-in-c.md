# 在 C++ 中提升()函数

> 原文:[https://www.geeksforgeeks.org/raise-function-in-c/](https://www.geeksforgeeks.org/raise-function-in-c/)

**cssignal**头文件声明了函数 **raise()** 来处理特定的信号。Signal 学习程序中的一些异常行为，并调用信号处理程序。实现它是为了检查默认处理程序是被调用还是被忽略。

**语法:**

```cpp
int raise ( int signal_ )
```

**参数:**该功能接受单个参数**信号**，该信号指定了人工提升的信号。它可以接收 6 个标准信号中的任何一个。
**定义的信号类型**

*   -是啊
*   信号情报
*   西格尔瑟夫
*   是 SIGTERM
*   西格布
*   西格弗

**返回值:**返回非零值，信号无错误，否则返回零。该函数返回具有不同定义信号的不同非零元素。

以下程序说明了上述方法:
**程序 1:**

```cpp
// C++ program to illustrate the
// raise() function when SIGABRT is passed
#include <csignal>
#include <iostream>
using namespace std;

sig_atomic_t s_value = 0;
void handle(int signal_)
{
    s_value = signal_;
}

int main()
{
    signal(SIGABRT, handle);
    cout << "Before called Signal = " << s_value << endl;
    raise(SIGABRT);
    cout << "After called Signal = " << s_value << endl;
    return 0;
}
```

**Output:**

```cpp
Before called Signal = 0
After called Signal = 6

```

**程序 2:**

```cpp
// C++ program to illustrate the
// raise() function when SIGINT is passed
#include <csignal>
#include <iostream>
using namespace std;

sig_atomic_t s_value = 0;
void handle(int signal_)
{
    s_value = signal_;
}

int main()
{
    signal(SIGINT, handle);
    cout << "Before called Signal = " << s_value << endl;
    raise(SIGINT);
    cout << "After called Signal = " << s_value << endl;
    return 0;
}
```

**Output:**

```cpp
Before called Signal = 0
After called Signal = 2

```

**程序 3:**

```cpp
// C++ program to illustrate the
// raise() function when SIGTERM is passed
#include <csignal>
#include <iostream>
using namespace std;

sig_atomic_t s_value = 0;
void handle(int signal_)
{
    s_value = signal_;
}

int main()
{
    signal(SIGTERM, handle);
    cout << "Before called Signal = " << s_value << endl;
    raise(SIGTERM);
    cout << "After called Signal = " << s_value << endl;
    return 0;
}
```

**Output:**

```cpp
Before called Signal = 0
After called Signal = 15

```

**程序 4:**

```cpp
// C++ program to illustrate the
// raise() function when SIGSEGV is passed
#include <csignal>
#include <iostream>
using namespace std;

sig_atomic_t s_value = 0;
void handle(int signal_)
{
    s_value = signal_;
}

int main()
{
    signal(SIGSEGV, handle);
    cout << "Before called Signal = " << s_value << endl;
    raise(SIGSEGV);
    cout << "After called Signal = " << s_value << endl;
    return 0;
}
```

**Output:**

```cpp
Before called Signal = 0
After called Signal = 11

```

**程序 5:**

```cpp
// C++ program to illustrate the
// raise() function when SIGFPE is passed
#include <csignal>
#include <iostream>
using namespace std;

sig_atomic_t s_value = 0;
void handle(int signal_)
{
    s_value = signal_;
}

int main()
{
    signal(SIGFPE, handle);
    cout << "Before called Signal = " << s_value << endl;
    raise(SIGFPE);
    cout << "After called Signal = " << s_value << endl;
    return 0;
}
```

**Output:**

```cpp
Before called Signal = 0
After called Signal = 8

```