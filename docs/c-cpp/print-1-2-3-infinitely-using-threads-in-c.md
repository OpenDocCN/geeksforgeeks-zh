# 使用 C

中的线程无限打印 1 2 3

> 原文:[https://www . geesforgeks . org/print-1-2-3-无限使用线程-in-c/](https://www.geeksforgeeks.org/print-1-2-3-infinitely-using-threads-in-c/)

用线无限打印 1 2 3。创建三个线程，即 T1、T2 和 T3，这样它们将无限地打印 1 2 3 序列。

**示例:**

```cpp
Output :1 2 3 1 2 3 1 2 3 1 2 3 1 2 3 ......

```

**先决条件:**C 中的[线程](https://www.geeksforgeeks.org/multithreading-c-2/)

**进场:**

*   开始无限循环，并将变量“done”初始化为 1。
*   现在，检查 done 的值是否不等于 1。
*   如果是保持等待条件锁定，则打印 n 并分别发出下一个连续 n 的信号。

```cpp
// C code to print 1 2 3 infinitely using pthread
#include <stdio.h>
#include <pthread.h>

// Declaration of thread condition variables
pthread_cond_t cond1  = 
               PTHREAD_COND_INITIALIZER;
pthread_cond_t cond2  = 
               PTHREAD_COND_INITIALIZER;
pthread_cond_t cond3  = 
               PTHREAD_COND_INITIALIZER;

// mutex which we are going to
// use avoid race condition.
pthread_mutex_t lock = PTHREAD_MUTEX_INITIALIZER;

// done is a global variable which decides 
// which waiting thread should be scheduled
int done = 1;

// Thread function
void *foo(void *n)
{
        while(1) {

                // acquire a lock
                pthread_mutex_lock(&lock);

                if (done != (int)*(int*)n) {

                        // value of done and n is not equal,
                        // hold wait lock on condition variable
                        if ((int)*(int*)n == 1) {
                                pthread_cond_wait(&cond1, &lock);
                        } else if ((int)*(int*)n == 2) {
                                pthread_cond_wait(&cond2, &lock);
                        }
                        else {
                                pthread_cond_wait(&cond3, &lock);
                        }

                }
                // done is equal to n, then print n
                printf("%d  ", *(int*)n);

                // Now time to schedule next thread accordingly 
                // using pthread_cond_signal()
                if (done == 3) {
                        done = 1;
                        pthread_cond_signal(&cond1);
                }
                else if(done == 1) {
                        done = 2;
                        pthread_cond_signal(&cond2);
                } else if (done == 2) {
                        done = 3;
                        pthread_cond_signal(&cond3);
                }

                // Finally release mutex
                pthread_mutex_unlock(&lock);
        }

        return NULL;
}

// Driver code
int main()
{
        pthread_t  tid1, tid2, tid3;
        int n1 = 1, n2 = 2, n3 = 3;

        // Create 3 threads 
        pthread_create(&tid1, NULL, foo, (void *)&n1);
        pthread_create(&tid2, NULL, foo, (void *)&n2);
        pthread_create(&tid3, NULL, foo, (void *)&n3);

        // infinite loop to avoid exit of a program/process
        while(1);

        return 0;
}
```

输出:

```cpp
1 2 3 1 2 3 1 2 3 1 2 3 ...

```