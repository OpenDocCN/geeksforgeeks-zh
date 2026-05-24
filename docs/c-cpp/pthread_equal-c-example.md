# C 中的 pthread_equal()带有示例

> 原文:[https://www.geeksforgeeks.org/pthread_equal-c-example/](https://www.geeksforgeeks.org/pthread_equal-c-example/)

先决条件:[多线程](https://www.geeksforgeeks.org/multithreading-c-2/)， [pthread_self()用实例](https://www.geeksforgeeks.org/pthread_self-c-example/)C

pthread_equal() =这将比较两个线程是否相等。该函数比较两个线程标识符。它返回“0”和非零值。如果相等，则返回非零值，否则返回 0。

**语法:- int pthread_equal (pthread_t t1，pthread _ t T2)；**

**第一种方法** :-与自螺纹

```cpp
// C program to demonstrate working of pthread_equal()
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/types.h>
#include <pthread.h>

pthread_t tmp_thread;

void* func_one(void* ptr)
{
    // in this field we can compare two thread
    // pthread_self gives a current thread id
    if (pthread_equal(tmp_thread, pthread_self())) {
        printf("equal\n");
    } else {
        printf("not equal\n");
    }
}

// driver code
int main()
{
    // thread one
    pthread_t thread_one;

    // assign the id of thread one in temporary
    // thread which is global declared   r
    tmp_thread = thread_one;

    // create a thread
    pthread_create(&thread_one, NULL, func_one, NULL);

    // wait for thread
    pthread_join(thread_one, NULL);
}
```

比较

输出:

```cpp
equal

```

**第二种方法** :-与其他螺纹

```cpp
// C program to demonstrate working of pthread_equal()
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/types.h>
#include <pthread.h>

// global declared pthread_t variable
pthread_t tmp_thread;

void* func_one(void* ptr)
{
    tmp_thread = pthread_self(); // assign the id of thread one in
    // temporary thread which is global declared
}

void* func_two(void* ptr)
{
    pthread_t thread_two = pthread_self();

    // compare two thread
    if (pthread_equal(tmp_thread, thread_two)) {
        printf("equal\n");
    } else {
        printf("not equal\n");
    }
}

int main()
{
    pthread_t thread_one, thread_two;

    // creating thread one
    pthread_create(&thread_one, NULL, func_one, NULL);

    // creating thread two
    pthread_create(&thread_two, NULL, func_two, NULL);

    // wait for thread one
    pthread_join(thread_one, NULL);

    // wait for thread two
    pthread_join(thread_two, NULL);
}
```

比较

输出:

```cpp
not equal

```

本文由**德万舒·阿加瓦尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。