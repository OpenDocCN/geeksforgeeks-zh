# c++ 中的线程可连接()函数

> 原文:[https://www . geesforgeks . org/thread-joined-function-in-c/](https://www.geeksforgeeks.org/thread-joinable-function-in-c/)

**Thread::joinable** 是 C++ std::thread 中的内置函数。它是一个观察者函数，这意味着它观察一个状态，然后返回相应的输出，并检查线程对象是否可连接。

如果线程对象标识/表示活动的执行线程，则称其是可连接的。

在下列情况下，线程不可连接:

*   它是默认构建的
*   如果已经调用了其成员联接或分离
*   它已经被移到其他地方了

**语法:**

```cpp
std::thread::joinable()

```

**参数:**此功能不接受任何参数。

**返回值:**是布尔型函数，当线程对象为
可连接时返回 true。如果线程对象不可连接，则返回 false。

以下程序演示了 std::thread::joinable()的使用

**注意:**在联机 IDE 上，这个程序会显示错误。要编译这个，在命令**“g++–STD = c++ 14-pthread file . CPP”**的帮助下，使用 g++ 编译器编译上的标志“-pthread”。

```cpp
// C++ program to demonstrate the use of
// std::thread::joinable()

#include <chrono>
#include <iostream>
#include <thread>

using namespace std;

// function to put thread to sleep
void threadFunc()
{
    std::this_thread::sleep_for(
        std::chrono::seconds(1));
}

int main()
{
    std::thread t1; // declaring the thread

    cout << "t1 joinable when default created? \n";
    // checking if it is joinable
    if (t1.joinable())
        cout << "YES\n";
    else
        cout << "NO\n";

    // calling the function threadFunc
    // to put thread to sleep
    t1 = std::thread(threadFunc);

    cout << "t1 joinable when put to sleep? \n";

    // checking if t1 is joinable
    if (t1.joinable())
        cout << "YES\n";
    else
        cout << "NO\n";

    // joining t1
    t1.join();

    // checking joinablity of t1 after calling join()
    cout << "t1 joinable after join is called? \n";
    if (t1.joinable())
        cout << "YES\n";
    else
        cout << "NO\n";

    return 0;
}
```

**输出:**

```cpp
t1 joinable when default created? 
NO
t1 joinable when put to sleep? 
YES
t1 joinable after join is called? 
NO

```

**注意:**第三个输出将在 1 秒后出现，因为线程被休眠了 1 分钟。