# C/c++

中的线程函数

> 原文:[https://www.geeksforgeeks.org/thread-functions-in-c-c/](https://www.geeksforgeeks.org/thread-functions-in-c-c/)

在一个 **Unix/Linux 操作系统**中， **C/C++ 语言**为所有线程相关的功能提供了 [POSIX 线程(pthread)](https://www.geeksforgeeks.org/multithreading-c-2/) 标准 API(应用程序接口)。它允许我们为并发进程流创建多个线程。它在多处理器或多核系统上最有效，在这些系统中，线程可以在内核级实现，以达到执行速度。在单处理器系统中，通过利用输入输出或其他可能导致进程停止的系统功能的延迟，也可以获得收益。

我们必须在脚本的开头包含 pthread.h 头文件，才能使用 pthreads 库的所有功能。要执行 c 文件，我们必须在编译文件时在命令行中使用-pthread 或-lpthread。

```cpp
cc -pthread file.c or
cc -lpthread file.c

```

在 **pthreads 库**中定义的**功能**包括:

1.  ***pthread_create:*** used to create a new thread

    **语法:**

    ```cpp
    int pthread_create(pthread_t * thread, 
                       const pthread_attr_t * attr, 
                       void * (*start_routine)(void *), 
                       void *arg);

    ```

    **参数:**

    *   **线程:**指向无符号整数值的指针，该整数值返回所创建线程的线程 id。
    *   **attr:** 指向用于定义线程属性(如分离状态、调度策略、堆栈地址等)的结构的指针。默认线程属性设置为空。
    *   **start_routine:** 指向线程正在执行的子例程的指针。子程序的返回类型和参数类型必须是 void *类型。该函数只有一个属性，但是如果需要将多个值传递给该函数，则必须使用一个结构。
    *   **arg:** 指向 void 的指针，该指针包含前面参数中定义的函数的参数
2.  ***pthread_exit:*** used to terminate a thread

    **语法:**

    ```cpp
    void pthread_exit(void *retval);

    ```

    **参数:**这个方法接受一个强制参数 **retval** ，它是一个整数的指针，用来存储线程终止的返回状态。该变量的范围必须是全局的，以便任何等待加入该线程的线程都可以读取返回状态。

3.  ***pthread_join:*** used to wait for the termination of a thread.

    **语法:**

    ```cpp
    int pthread_join(pthread_t th, 
                     void **thread_return);

    ```

    **参数:**该方法接受以下参数:

    *   **th:** 当前线程等待的线程的线程 id。
    *   **thread_return:** 指向存储 th 中提到的线程退出状态的位置的指针。
4.  ***pthread_self:*** used to get the thread id of the current thread.

    **语法:**

    ```cpp
    pthread_t pthread_self(void);

    ```

5.  ***pthread_equal:*** compares whether two threads are the same or not. If the two threads are equal, the function returns a non-zero value otherwise zero.

    **语法:**

    ```cpp
    int pthread_equal(pthread_t t1, 
                      pthread_t t2);

    ```

    **参数:**该方法接受以下参数:

    *   t1:第一个线程的线程 id
    *   t2:第二个线程的线程 id
6.  ***pthread_cancel:*** used to send a cancellation request to a thread

    **语法:**

    ```cpp
    int pthread_cancel(pthread_t thread);

    ```

    **参数:**此方法接受一个强制参数**线程**，它是被发送取消请求的线程的线程 id。

7.  ***pthread_detach:*** used to detach a thread. A detached thread does not require a thread to join on terminating. The resources of the thread are automatically released after terminating if the thread is detached.

    **语法:**

    ```cpp
    int pthread_detach(pthread_t thread);

    ```

    **参数:**该方法接受一个强制参数**螺纹**，即必须拆卸的螺纹的螺纹 id。

**示例:**线程的简单实现可能如下:

```cpp
// C program to show thread functions

#include <pthread.h>
#include <stdio.h>
#include <stdlib.h>

void* func(void* arg)
{
    // detach the current thread
    // from the calling thread
    pthread_detach(pthread_self());

    printf("Inside the thread\n");

    // exit the current thread
    pthread_exit(NULL);
}

void fun()
{
    pthread_t ptid;

    // Creating a new thread
    pthread_create(&ptid, NULL, &func, NULL);
    printf("This line may be printed"
           " before thread terminates\n");

    // The following line terminates
    // the thread manually
    // pthread_cancel(ptid);

    // Compare the two threads created
    if(pthread_equal(ptid, pthread_self())
        printf("Threads are equal\n");
    else
        printf("Threads are not equal\n");

    // Waiting for the created thread to terminate
    pthread_join(ptid, NULL);

    printf("This line will be printed"
           " after thread ends\n");

    pthread_exit(NULL);
}

// Driver code
int main()
{
    fun();
    return 0;
}
```

**输出:**

```cpp
This line may be printed before thread terminates
Threads are not equal
Inside the thread
This line will be printed after thread ends

```

**说明:**这里在代码中创建了两个执行线程。两个线程的输出行的顺序可以根据之前处理的线程而互换。主线程等待新创建的线程退出。因此，只有在新线程退出后，才会打印输出的最后一行。通过不使用 *pthread_join* 功能，线程可以彼此独立终止。如果我们想手动终止新线程，我们可以使用 *pthread_cancel* 来完成。

**注意:**如果我们使用 exit()而不是 **pthread_exit()** 来结束一个线程，那么具有所有关联线程的整个进程将被终止，即使其中一些线程可能仍在运行。