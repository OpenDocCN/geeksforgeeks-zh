# c++ 中的 Thread hardware_concurrency()函数

> 原文:[https://www . geesforgeks . org/thread-hardware _ concurrency-function-in-c/](https://www.geeksforgeeks.org/thread-hardware_concurrency-function-in-c/)

**Thread::hardware _ concurrency**是 C++ std::thread 中的内置函数。它是一个**观测器函数**，这意味着它观测一个状态，然后返回相应的输出。该函数返回**可用硬件实现支持的并发线程数**。该值可能并不总是准确的。

**语法:**

```cpp
thread::hardware_concurrency()
```

**参数:**此功能不接受任何参数。

**返回值:**返回一个非负整数，表示系统支持的**并发线程数**。如果该值不可计算或定义不明确，则返回 0。

下面的程序演示了 std::thread::joinable()的用法

**注意:**在线 IDE 上这个程序会显示错误。要编译这个，在命令“**g++–STD = c++ 14-pthread file . CPP**”的帮助下，使用 g++ 编译器编译上的标志“-pthread”。

```cpp
// C++ program to demonstrate the use of
// std::thread::hardware_concurrency()

#include <chrono>
#include <iostream>
#include <thread>
using namespace std;

int main()
{
    unsigned int con_threads;

    // calculating number of concurrent threads
    // supported in the hardware implementation
    con_threads = thread::hardware_concurrency();

    cout << "Number of concurrent threads supported are: "
         << con_threads << endl;

    return 0;
}
```

**可能的输出**

```cpp
Number of concurrent threads supported are: 4
```