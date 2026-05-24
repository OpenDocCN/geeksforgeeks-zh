# c++ 中的多线程

> 原文:[https://www.geeksforgeeks.org/multithreading-in-cpp/](https://www.geeksforgeeks.org/multithreading-in-cpp/)

C+11 引入了多线程支持。在 C++ 11 之前，我们不得不在 C 中使用 [POSIX 线程或者 p 线程库。虽然这个库完成了工作，但是缺少任何标准语言提供的特性集导致了严重的可移植性问题。C++ 11 抛弃了所有这些，给了我们 **std::thread** 。线程类和相关函数在**线程**头文件中定义。](https://www.geeksforgeeks.org/multithreading-c-2/)

**std::thread** 是 C++ 中表示单线程的线程类。要启动一个线程，我们只需要创建一个新的线程对象，并将要调用的执行代码(即一个可调用对象)传递给该对象的构造函数。一旦对象被创建，一个新的线程就被启动，它将执行在 callable 中指定的代码。

可调用的可以是这三种中的任何一种

*   函数指针
*   函数对象
*   λ表达式

    定义可调用后，将其传递给构造函数。

    ```cpp
    #include<thread>
    std::thread thread_object(callable)
    ```

    **使用函数指针**
    启动线程下面的代码片段演示了这是如何实现的

    ```cpp
    void foo(param)
    {
        // Do something
    }

    // The parameters to the function are put after the comma
    std::thread thread_obj(foo, params);
    ```

    **使用λ表达式启动线程**

    下面的代码片段演示了如何做到这一点

    ```cpp
    // Define a lamda expression
    auto f = [](params) {
        // Do Something
    };

    // Pass f and its parameters to thread 
    // object constructor as
    std::thread thread_object(f, params);
    ```

    我们还可以将 lambda 函数直接传递给构造函数。

    ```cpp
    std::thread thread_object([](params) {
        // Do Something
    };, params);
    ```

    **使用功能对象启动线程**

    下面的代码片段演示了如何做到这一点

    ```cpp
    // Define the class of function object
    class fn_object_class {
        // Overload () operator
        void operator()(params)
        {
            // Do Something
        }
    }

    // Create thread object
    std::thread thread_object(fn_object_class(), params)
    ```

    **等待线程完成**

    一旦线程启动，我们可能需要等待线程完成，然后才能采取一些行动。例如，如果我们将初始化应用程序图形用户界面的任务分配给一个线程，我们需要等待线程完成，以确保图形用户界面已经正确加载。

    要等待线程，请使用 **std::thread::join()** 函数。该功能使当前线程等待，直到***该**标识的线程执行完毕。
    例如，要阻塞主线程直到线程 t1 完成，我们需要做的是

    ```cpp
    int main()
    {
        // Start thread t1
        std::thread t1(callable);

        // Wait for t1 to finish
        t1.join();

        // t1 has finished do other stuff

        ...
    }
    ```

    **一个完整的 C++ 程序**

    下面给出了一个 C++ 程序。它从主函数中启动三个线程。使用上面指定的可调用对象之一调用每个线程。

    ```cpp
    // CPP program to demonstrate multithreading
    // using three different callables.
    #include <iostream>
    #include <thread>
    using namespace std;

    // A dummy function
    void foo(int Z)
    {
        for (int i = 0; i < Z; i++) {
            cout << "Thread using function"
                   " pointer as callable\n";
        }
    }

    // A callable object
    class thread_obj {
    public:
        void operator()(int x)
        {
            for (int i = 0; i < x; i++)
                cout << "Thread using function"
                      " object as  callable\n";
        }
    };

    int main()
    {
        cout << "Threads 1 and 2 and 3 "
             "operating independently" << endl;

        // This thread is launched by using 
        // function pointer as callable
        thread th1(foo, 3);

        // This thread is launched by using
        // function object as callable
        thread th2(thread_obj(), 3);

        // Define a Lambda Expression
        auto f = [](int x) {
            for (int i = 0; i < x; i++)
                cout << "Thread using lambda"
                 " expression as callable\n";
        };

        // This thread is launched by using 
        // lamda expression as callable
        thread th3(f, 3);

        // Wait for the threads to finish
        // Wait for thread t1 to finish
        th1.join();

        // Wait for thread t2 to finish
        th2.join();

        // Wait for thread t3 to finish
        th3.join();

        return 0;
    }
    ```

    输出(取决于机器)

    ```cpp
    Threads 1 and 2 and 3 operating independently                                                       
    Thread using function pointer as callable                                                           
    Thread using lambda expression as callable                                                          
    Thread using function pointer as callable                                                           
    Thread using lambda expression as callable                                                          
    Thread using function object as  callable                                                          
    Thread using lambda expression as callable                                                          
    Thread using function pointer as callable                                                          
    Thread using function object as  callable                                                           
    Thread using function object as  callable

    ```

    注意:
    要编译支持 std::thread 的程序，请使用

    ```cpp
    g++ -std=c++ 11 -pthread

    ```

    参考
    [CP preference–螺纹](https://en.cppreference.com/w/cpp/thread)