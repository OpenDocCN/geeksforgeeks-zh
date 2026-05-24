# c++ 中线程 get_id()函数

> 原文:[https://www.geeksforgeeks.org/thread-get_id-function-in-c/](https://www.geeksforgeeks.org/thread-get_id-function-in-c/)

**Thread::get_id()** 是 C++ std::thread 中的内置函数。它是一个观察函数，这意味着它观察一个状态，然后返回相应的输出。此函数返回 std::thread::id 的值，从而识别与此关联的线程。
**语法:**

```cpp
thread_name.get_id();
```

**参数:**此功能不接受任何参数。
**返回值:**该方法返回一个类型为 **std::thread::id** 的值，该值标识与该*关联的线程，即返回用于调用 get_id 函数的**线程。当没有识别到这样的线程时，返回**默认构造的 std::thread::id** 。
下面的例子演示了 std::thread::get_id()方法的使用:
**注意**:在线 IDE 上这个程序会显示错误。要编译这个，在命令“**g++–STD = c++ 14-pthread file . CPP**”的帮助下，使用 g++ 编译器编译上的标志“-pthread”。** 

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate the use of
// std::thread::get_id

#include <chrono>
#include <iostream>
#include <thread>
using namespace std;

// util function for thread creation
void sleepThread()
{
    this_thread::sleep_for(chrono::seconds(1));
}

int main()
{
    // creating thread1 and thread2

    thread thread1(sleepThread);
    thread thread2(sleepThread);

    thread::id t1_id = thread1.get_id();
    thread::id t2_id = thread2.get_id();

    cout << "ID associated with thread1= "
         << t1_id << endl;
    cout << "ID associated with thread2= "
         << t2_id << endl;

    thread1.join();
    thread2.join();

    return 0;
}
```

**可能的输出:**

```cpp
ID associated with thread1= 139858743162624
ID associated with thread2= 139858734769920
```