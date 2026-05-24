# pthread_getcpuclockid()函数在 C 中用实例

> 原文:[https://www . geeksforgeeks . org/pthread _ getcpuclockid-function-in-c-with-examples/](https://www.geeksforgeeks.org/pthread_getcpuclockid-function-in-c-with-examples/)

**pthread_getcpuclockid()** 函数从指定线程返回 CPU 时间时钟的时钟标识。

**语法:**

> int pthread _ getcpuclock id(pthread _ t id，clock kid _ t * clock _ id)；

**参数:**该方法接受以下参数:

*   **线程:**要获取时钟 ID 的线程的 ID，调用 pthread_create()或 pthread_self()都可以获取。
*   **clock_id:** 指向 clockid _ t 对象的指针，函数可以在该对象中存储时钟 id。

**返回值:**此方法返回特定线程的 CPU 时钟时间。

下面是一些示例，展示了 pthread_getcpuclockid()方法的实现:

**示例 1:** 下面的程序创建一个线程，然后使用 clock_gettime(2)检索两个线程消耗的总进程 CPU 时间和每线程 CPU 时间。

## C

```cpp
// C program to implement
// the above approach
#include <errno.h>
#include <pthread.h>
#include <stdint.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <time.h>
#include <unistd.h>

#define handle_error(msg) \
    do
{
    perror(msg);
    exit(EXIT_FAILURE);
}
while (0)

#define handle_error_en(en, msg) \
    do
{
    errno = en;
    perror(msg);
    exit(EXIT_FAILURE);
}
while (0)

    static void* thread_start(void* arg)
    {
        printf(
            "Subthread starting infinite loop\n");
        for (;;)
            continue;
    }

static void pclock(char* msg,
                   clockid_t cid)
{
    struct timespec ts;
    printf("%s", msg);

    if (clock_gettime(cid,
                      &ts)
        == -1)
        handle_error("clock_gettime");
    printf("%4jd.%03ld\n",
           (intmax_t)ts.tv_sec,
           ts.tv_nsec / 1000000);
}

// Driver code
int main(int argc,
         char* argv[])
{
    pthread_t thread;
    clockid_t cid;
    int s;
    s = pthread_create(&thread, NULL,
                       thread_start, NULL);

    if (s != 0)
        handle_error_en(s, "pthread_create");

    printf("Main thread sleeping\n");
    sleep(1);

    printf(
        "Main thread consuming some CPU time...\n");

    for (int j = 0; j < 2000000; j++)
        getppid();

    pclock("Process total CPU time: ",
           CLOCK_PROCESS_CPUTIME_ID);
    s = pthread_getcpuclockid(pthread_self(),
                              &cid);

    if (s != 0)
        handle_error_en(s, "pthread_getcpuclockid");

    pclock("Main thread CPU time:   ",
           cid);

    /* The preceding 4 lines of code could 
     have been replaced by:
     pclock("Main thread CPU time:   ", 
             CLOCK_THREAD_CPUTIME_ID); */
    s = pthread_getcpuclockid(thread, &cid);

    if (s != 0)
        handle_error_en(s, "pthread_getcpuclockid");

    pclock("Subthread CPU time: 1    ",
           cid);

    // Terminates both threads
    exit(EXIT_SUCCESS);
}
```

**输出:**

> $ ./a.out
> 主线程休眠
> 子线程启动无限循环
> 主线程消耗部分 CPU 时间……
> 进程总 CPU 时间:1.368
> 主线程 CPU 时间:0.376
> 子线程 CPU 时间:0.992

**示例 2:** 下面的程序创建一个进程，然后使用 clock_gettime(2)检索两个进程消耗的总进程 CPU 时间以及父进程和子进程 CPU 时间。

## C

```cpp
// C program to implement
// the above approach
#include <pthread.h>
#include <stdio.h>
#include <time.h>

pthread_cond_t cond2;
pthread_condattr_t cond2attr;

#define test(clk_id) \
    {                \
    printf("%s:%d\n",
#clk_id, clk_id);
           }

static void print_clock(char* msg,
                        clockid_t cid)
{
    struct timespec ts;

    printf("%s", msg);

    if (clock_gettime(cid, &ts) == -1)
        fprintf(stderr,
                "clock_gettime");

    printf("%4ld.%03ld\n",
           ts.tv_sec,
           ts.tv_nsec / 1000000);
}

void* test_task_fn(void* unused)
{
    printf("test_task_fn.\n");

    for (;;)
        continue;

    static int status = 12121;

    pthread_exit(&status);
    return NULL;
}

// Driver code
int main()
{
    int* pstatus;
    int ret;
    clockid_t clockid = 0;
    pthread_t thread_id;

    pthread_create(&thread_id, NULL,
                   test_task_fn, NULL);

    printf("Main thread sleeping\n");
    sleep(1);

    ret = pthread_getcpuclockid(
        thread_id, &clockid);
    print_clock("  Child", clockid);

    ret = pthread_getcpuclockid(
        pthread_self(), &clockid);
    print_clock(" Parent",
                clockid);
    print_clock("Process",
                CLOCK_PROCESS_CPUTIME_ID);

    pthread_join(thread_id,
                 (void**)&pstatus);

    printf("pstatus = %d\n",
           *pstatus);

    return 0;
}
```

**输出:**

> [root@localhost pthread]#。/compile . sh pthread _ getcpuclockid . c
> [root @ localhost pthread]#。/a.out
> 主线程休眠
> 测试 _ 任务 _fn。
> 子 0.999
> 父 0.001
> 流程 1.000