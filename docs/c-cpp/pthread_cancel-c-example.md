# C 中的 pthread_cancel()，示例

> 原文:[https://www.geeksforgeeks.org/pthread_cancel-c-example/](https://www.geeksforgeeks.org/pthread_cancel-c-example/)

**先决条件:[多线程](https://www.geeksforgeeks.org/multithreading-c-2/)、 [pthread_self()在 C 用例](https://www.geeksforgeeks.org/pthread_self-c-example/)**

pthread_cancel() =该函数使用线程 id 取消特定的线程。这个函数向线程发送一个取消请求。

**语法:–int pthread _ cancel(pthread _ t 线程)；**

**第一个程序:–**取消自线程

```cpp
// C program to demonstrates cancellation of self thread 
// using thread id
#include <stdio.h>
#include <stdlib.h>
#include <pthread.h>

void* calls(void* ptr)
{
    printf("GeeksForGeeks");

    // To exit the current thread
    // pthread_self() return the particular thread id
    pthread_cancel(pthread_self()); 

    return NULL;
}

int main()
{
    // NULL when no attribute
    pthread_t thread;

    // calls is a function name
    pthread_create(&thread, NULL, calls, NULL); 

    // Waiting for when thread is completed
    pthread_join(thread, NULL); 

    return 0;
}
```

**输出:**

```cpp
GeeksForGeeks

```

如果你使用 Linux，那么编译这个程序**gcc program _ name . c-lpthread**

**第二个程序:–**取消其他线程

```cpp
// C program to demonstrates cancellation of another thread 
// using thread id
#include <stdio.h>
#include <unistd.h>
#include <sys/types.h>
#include <pthread.h>

// To Count
int counter = 0; 

// for temporary thread which will be 
// store thread id of second thread
pthread_t tmp_thread; 

// thread_one call func
void* func(void* p) 
{
    while (1) {

        printf("thread number one\n");
        sleep(1);   // sleep 1 second
        counter++ ;   

        // for exiting if counter = = 5
        if (counter = = 2) {

            // for cancel thread_two
            pthread_cancel(tmp_thread); 

            // for exit from thread_one 
            pthread_exit(NULL);  
        }
    }
}

// thread_two call func2
void* func2(void* p) 
{

    // store thread_two id to tmp_thread
    tmp_thread = pthread_self(); 

    while (1) {
        printf("thread Number two");
        sleep(1); // sleep 1 second
    }
}

// Driver code
int main()
{

    // declare two thread
    pthread_t thread_one, thread_two; 

    // create thread_one
    pthread_create(&thread_one, NULL, func, NULL);

    // create thread_two 
    pthread_create(&thread_two, NULL, func2, NULL); 

    // waiting for when thread_one is completed
    pthread_join(thread_one, NULL); 

    // waiting for when thread_two is completed
    pthread_join(thread_two, NULL); 

}
```

**输出:**

```cpp
thread number one
thread number two
thread number one 
thread number two

```

如果你使用 Linux，那么编译这个程序**gcc program _ name . c-lpthread**

本文由**德万舒·阿加瓦尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。