# C 中的 pthread_self()，示例

> 原文:[https://www.geeksforgeeks.org/pthread_self-c-example/](https://www.geeksforgeeks.org/pthread_self-c-example/)

前提条件:[C 中多线程](https://www.geeksforgeeks.org/multithreading-c-2/)

**语法:-pthread _ t pthread _ self(void)；**

pthread _ self()函数返回调用它的线程的 ID。

```cpp
// C program to demonstrate working of pthread_self()
#include <stdio.h>
#include <stdlib.h>
#include <pthread.h>
void* calls(void* ptr)
{
    // using pthread_self() get current thread id
    printf("In function \nthread id = %d\n", pthread_self());
    pthread_exit(NULL);
    return NULL;
}

int main()
{
    pthread_t thread; // declare thread
    pthread_create(&thread, NULL, calls, NULL);
    printf("In main \nthread id = %d\n", thread); 
    pthread_join(thread, NULL); 
    return 0;
}
```

**输出:**

```cpp
In function
thread id = 1
In main
thread id = 1

```

本文由**德万舒·阿加瓦尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。