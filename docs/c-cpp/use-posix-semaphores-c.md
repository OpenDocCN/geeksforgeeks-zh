# 如何用 C 语言使用 POSIX 信号量

> 原文:[https://www.geeksforgeeks.org/use-posix-semaphores-c/](https://www.geeksforgeeks.org/use-posix-semaphores-c/)

[信号量](https://www.geeksforgeeks.org/semaphores-operating-system/)在进程同步和多线程中非常有用。但是在现实生活中如何使用呢，比如说用 C 语言？

我们在 Linux 系统中有 POSIX 信号量库。让我们学习如何使用它。

信号量的基本代码很简单，如这里的所示。但是这种代码不能直接编写，因为函数需要是原子的，直接编写代码会导致没有函数完成的上下文切换，并且会导致混乱。

Linux 中的 POSIX 系统提供了自己的内置信号量库。要使用它，我们必须:

1.  包含信号量
2.  Compile the code by linking with -lpthread -lrt

    要锁定信号量或等待，我们可以使用 **sem_wait** 功能:

    ```cpp
    int sem_wait(sem_t *sem);
    ```

    要释放或发出信号，我们使用 **sem_post** 功能:

    ```cpp
    int sem_post(sem_t *sem);
    ```

    信号量通过使用 **sem_init** (对于进程或线程)或 **sem_open** (对于进程间通信)来初始化。

    ```cpp
    sem_init(sem_t *sem, int pshared, unsigned int value);
    ```

    哪里，

    *   **sem** :指定要初始化的信号量。
    *   **pshared** :此参数指定新初始化的信号量是在进程之间共享还是在线程之间共享。非零值表示信号量在进程间共享，零值表示信号量在线程间共享。
    *   **值**:指定分配给新初始化信号量的值。

    要破坏一个信号量，我们可以使用 **sem_destroy** 。

    ```cpp
    sem_destroy(sem_t *mutex);
    ```

    要声明一个信号量，数据类型是 sem_t。

    **代码–**

    ```cpp
    // C program to demonstrate working of Semaphores
    #include <stdio.h>
    #include <pthread.h>
    #include <semaphore.h>
    #include <unistd.h>

    sem_t mutex;

    void* thread(void* arg)
    {
        //wait
        sem_wait(&mutex);
        printf("\nEntered..\n");

        //critical section
        sleep(4);

        //signal
        printf("\nJust Exiting...\n");
        sem_post(&mutex);
    }

    int main()
    {
        sem_init(&mutex, 0, 1);
        pthread_t t1,t2;
        pthread_create(&t1,NULL,thread,NULL);
        sleep(2);
        pthread_create(&t2,NULL,thread,NULL);
        pthread_join(t1,NULL);
        pthread_join(t2,NULL);
        sem_destroy(&mutex);
        return 0;
    }
    ```

    编译应该使用 gcc a.c -lpthread -lrt 完成

    **解释–**
    正在创建 2 个线程，一个在第一个线程之后 2 秒。
    但是第一个线程在获取锁后会休眠 4 秒。
    因此第二个线程不会在被调用后立即进入，而是在被调用后 4–2 = 2 秒进入。
    所以输出是:

    ```cpp
    Entered..

    Just Exiting...

    Entered..

    Just Exiting...

    ```

    但不是:

    ```cpp
    Entered..

    Entered..

    Just Exiting...

    Just Exiting...

    ```

    本文由[掌门人 Dey](https://www.linkedin.com/in/suprotik-dey-368706127/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。