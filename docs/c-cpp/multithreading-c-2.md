# C 中多线程

> 原文:[https://www.geeksforgeeks.org/multithreading-c-2/](https://www.geeksforgeeks.org/multithreading-c-2/)

**什么是线？**
线程是进程中的单个序列流。因为线程具有进程的一些属性，所以它们有时被称为*轻量级进程*。

**进程和线程有什么区别？**
线程不像进程那样相互独立，因此线程与其他线程共享它们的代码段、数据段和操作系统资源，比如打开的文件和信号。但是，像进程一样，线程有自己的程序计数器(PC)、寄存器组和堆栈空间。

**为什么是多线程？**
线程是通过并行性提高应用程序的流行方式。例如，在浏览器中，多个选项卡可以是不同的线程。MS word 使用多个线程，一个线程格式化文本，另一个线程处理输入等。
线程比进程运行更快，原因如下:
1)线程创建更快。
2)线程之间的上下文切换要快得多。
3)线程可以轻松终止
4)线程之间的通信更快。

详见[http://www . personal . Kent . edu/~ rmu HAMA/OpSyStemS/Myo/threads . htm](http://www.personal.kent.edu/%7Ermuhamma/OpSystems/Myos/threads.htm)。

**我们能用 C 语言编写多线程程序吗？**
与 Java 不同，语言标准不支持多线程。 [POSIX 线程(或 Pthreads)](http://en.wikipedia.org/wiki/POSIX_Threads) 是线程的 POSIX 标准。gcc 编译器可以实现 pthread。

**一个简单的 C 程序演示 pthread 基本功能的使用**
请注意，下面的程序可能只能用带有 pthread 库的 C 编译器编译。

```cpp
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>  //Header file for sleep(). man 3 sleep for details.
#include <pthread.h>

// A normal C function that is executed as a thread 
// when its name is specified in pthread_create()
void *myThreadFun(void *vargp)
{
    sleep(1);
    printf("Printing GeeksQuiz from Thread \n");
    return NULL;
}

int main()
{
    pthread_t thread_id;
    printf("Before Thread\n");
    pthread_create(&thread_id, NULL, myThreadFun, NULL);
    pthread_join(thread_id, NULL);
    printf("After Thread\n");
    exit(0);
}
```

在 main()中，我们声明了一个名为 thread_id 的变量，该变量的类型为 pthread_t，它是一个整数，用于标识系统中的线程。在声明 thread_id 之后，我们调用 pthread_create()函数来创建一个线程。
pthread_create()接受 4 个参数。
第一个参数是一个指向 thread_id 的指针，由这个函数设置。
第二个参数指定属性。如果该值为空，则应使用默认属性。
第三个参数是要为要创建的线程执行的函数的名称。
第四个参数用于将参数传递给函数 myThreadFun。
线程的 pthread_join()函数相当于进程的 wait()。对 pthread_join 的调用阻塞调用线程，直到标识符等于第一个参数的线程终止。

**以上程序如何编译？**
要使用 gcc 编译多线程程序，我们需要将其与 pthreads 库链接。下面是用来编译程序的命令。

```cpp
gfg@ubuntu:~/$ gcc multithread.c -lpthread
gfg@ubuntu:~/$ ./a.out
Before Thread
Printing GeeksQuiz from Thread 
After Thread
gfg@ubuntu:~/$ 
```

**一个用全局和静态变量**
展示多个线程的 C 程序如上所述，所有线程共享数据段。全局变量和静态变量存储在数据段中。因此，它们由所有线程共享。下面的示例程序演示了相同的内容。

```cpp
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <pthread.h>

// Let us create a global variable to change it in threads
int g = 0;

// The function to be executed by all threads
void *myThreadFun(void *vargp)
{
    // Store the value argument passed to this thread
    int *myid = (int *)vargp;

    // Let us create a static variable to observe its changes
    static int s = 0;

    // Change static and global variables
    ++ s; ++ g;

    // Print the argument, static and global variables
    printf("Thread ID: %d, Static: %d, Global: %d\n", *myid, ++ s, ++ g);
}

int main()
{
    int i;
    pthread_t tid;

    // Let us create three threads
    for (i = 0; i < 3; i++)
        pthread_create(&tid, NULL, myThreadFun, (void *)&tid);

    pthread_exit(NULL);
    return 0;
}
```

```cpp
gfg@ubuntu:~/$ gcc multithread.c -lpthread
gfg@ubuntu:~/$ ./a.out
Thread ID: 3, Static: 2, Global: 2
Thread ID: 3, Static: 4, Global: 4
Thread ID: 3, Static: 6, Global: 6
gfg@ubuntu:~/$ 
```

请注意，上面是展示线程如何工作的简单示例。访问线程中的全局变量通常不是个好主意。如果线程 2 的优先级高于线程 1，而线程 1 需要更改变量，该怎么办。实际上，如果需要多个线程访问全局变量，那么应该使用互斥体来访问它们。

**参考文献:**
[http://www . CSC . villanova . edu/~ MDA mian/threads/POSIX threads . html](http://www.csc.villanova.edu/~mdamian/threads/posixthreads.html)
[计算机系统:一个程序员](http://www.flipkart.com/computer-systems-programmer-s-perspective-2nd/p/itmdx5gnnz8ynpsh?pid=9780136108047&affid=sandeepgfg)

本文由**拉胡尔·贾恩**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论