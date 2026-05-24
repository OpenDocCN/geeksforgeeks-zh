# 使用 C 语言的秒表

> 原文:[https://www.geeksforgeeks.org/stopwatch-using-c-language/](https://www.geeksforgeeks.org/stopwatch-using-c-language/)

用 C 语言创建一个数字秒表程序，运行在 linux 操作系统上。

**keyboardhit()** 功能简单代表键盘点击。按下一个键后，它会产生一个信号并返回一个非零整数。这里有 4 个循环，第一个循环持续小时，第二个循环持续分钟，第三个循环持续秒，第四个循环保持秒的速度(3 个循环)。运行该程序后，它等待键盘开始键被按下，当键被按下时，它产生一个信号。为了存储一个键盘键，有一个变量(c)，如果 c 等于 **p 键**，那么它调用等待函数。线程正在后台运行，我们正在等待开始键被按下。按下 s 键后，线程再次跳转到 thread_join 功能，如果按下 **r 键**，则跳转到 reset 标签，所有循环再次以零开始，如果按下 **s 键**，则跳转到 start 标签，如果按下 **e 键**，则调用 exit()功能，程序终止。

**先决条件:**c 中的[线程](https://www.geeksforgeeks.org/operarting-system-thread/)、[等待系统调用](https://www.geeksforgeeks.org/wait-system-call-c/)

```cpp
To execute the program we use following command :

```

```cpp
Input:
Press a key :
s -> start
e -> exit
r -> reset
p -> pause

Output :

```

```cpp
// C code to create stop watch

// Header file for necessary system library
#include <fcntl.h>
#include <pthread.h>
#include <stdio.h>
#include <stdlib.h>
#include <termios.h>
#include <unistd.h>

// starting from zero
#define MIN 0

// 1 hr= 60 min ; 1 min= 60 sec
#define MAX 60

#define MILLI 200000

int i, j, k, n, s;
char c;
pthread_t t1;

// Function to perform operations
// according keyboeard hit.
int keyboardhit(void)
{
    struct termios oldt, newt;
    int ch;
    int oldf;

    tcgetattr(STDIN_FILENO, &oldt);
    newt = oldt;
    newt.c_lflag &= ~(ICANON | ECHO);
    tcsetattr(STDIN_FILENO, TCSANOW, &newt);
    oldf = fcntl(STDIN_FILENO, F_GETFL, 0);
    fcntl(STDIN_FILENO, F_SETFL, oldf | O_NONBLOCK);

    ch = getchar();

    tcsetattr(STDIN_FILENO, TCSANOW, &oldt);
    fcntl(STDIN_FILENO, F_SETFL, oldf);

    if (ch != EOF) {
        ungetc(ch, stdin);
        return 1;
    }

    return 0;
}

// display stopwatch on screen
void print()
{
    // clear screen escape sequence
    printf("\033[2J\033[1;1H");

    // Display Hour Min Sec in screen
    printf("TIME\t\t\t\tHr: %d Min: %d Sec: %d", n, i, j);
}

// function to pause stopwatch
void* wait(void* arg)
{

    while (1) {

        // wait for keyboard signal if keyboard
        // hit it return non integer number
        if (keyboardhit()) {
            // take input from user and do
            // operation accordingly
            c = getchar();
            if (c == 'S' || c == 's') {
                break;
            }
            else if (c == 'r' || c == 'R') {
                s = 1;
                break;
            }
            else if (c == 'e' || c == 'E')

                exit(0);
        }
    }
}

// driver code
int main()
{

    // label to reset the value
reset:
    n = MIN;
    i = MIN;
    j = MIN;
    k = MIN, s = MIN;

    print();

    while (1) {

        /* s for start
        e for exit
        p for pause
        r for reset
        */
        if (keyboardhit()) {
            c = getchar();

            if (c != 's')
                continue;

            for (n = MIN; n < MAX; n++) {
                for (i = MIN; i < MAX; i++) {
                    for (j = MIN; j < MAX; j++) {
                        for (k = MIN; k < MILLI; k++) {
                        start:
                            print();
                            if (keyboardhit()) {
                                c = getchar();

                                if (c == 'r' || c == 'R')
                                    goto reset;
                                else if (c == 'e' || c == 'E')
                                    exit(0);
                                else if (c == 's' || c == 'S')
                                    goto start;
                                else if (c == 'P' || c == 'p') {

                                    pthread_create(&t1, NULL, &wait, NULL);

                                    // waiting for join a thread
                                    pthread_join(t1, NULL);
                                    if (s == 1)
                                        goto reset;
                                }
                            }
                        }
                    }
                }
            }
        }
    }

    return 0;
}
```

输出: