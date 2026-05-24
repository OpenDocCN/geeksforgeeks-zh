# C

中复杂的声明

> 原文:[https://www . geesforgeks . org/complex-declarations-in-c/](https://www.geeksforgeeks.org/complicated-declarations-in-c/)

大多数时候声明很容易阅读，但是很难阅读一些包含指向函数的指针的声明。例如，考虑下面来自“signal.h”的声明。

## C

```cpp
void (*bsd_signal(int, void (*)(int)))(int);
```

让我们看看阅读复杂声明的步骤。
**1)** 将 C 声明转换为后缀格式，从右向左读取。
**2)** 要将表达式转换为后缀，请从最里面的括号开始，如果最里面的括号不存在，则从声明名称开始，并首先向右。当遇到第一个结束括号时，向左拐。一旦整个括号被解析，那么就从括号中出来。
**3)** 继续，直到解析完完整的声明。
让我们从一个简单的例子开始。下面的例子来自《K & R》一书。

## C

```cpp
1)  int (*fp) ();
```

让我们把上面的表达式转换成后缀格式。对于上面的例子，没有最里面的括号，这就是为什么，我们将打印声明名称即“fp”。下一步是，转到表达式的右侧，但是“fp”的右侧没有任何内容需要解析，这就是为什么要转到左侧。在左侧我们找到“*”，现在打印“*”并从括号中出来。我们将得到如下后缀表达式。

```cpp
  fp  *  ()  int
```

现在从左向右读后缀表达式。例如 fp 是指向返回 int 的函数的指针

## C

```cpp
/* Example */

#include <stdio.h>
int (*fp)();
int func(void) { printf("hello\n"); }

int main()
{
    fp = func;
    (*fp)();
    // fp(); // This will also call func
    return 0;
}
```

**Output**

```cpp
hello
```

让我们看看更多的例子。

## C

```cpp
2) int (*daytab)[13]
```

后缀:daytab * [13] int
含义:daytab 是指向 13 个整数数组的指针。

## C

```cpp
/* Example */

#include <stdio.h>
int (*daytab)[13];
int arr[13] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13 };
int main()
{
    daytab = &arr;
    printf("arr[2] = %d\n", (*daytab)[2]);
    return 0;
}
```

**Output**

```cpp
arr[2] = 3
```

## C

```cpp
3) void (*f[10]) (int, int)
```

后缀:f[10] * (int，int) void
含义:f 是一个 10 个指针的数组，指向返回 void
的函数(它接受 int 类型的 2 个参数)

## C

```cpp
/* Example */

#include <stdio.h>
void (*f[10])(int, int);
void func1(int a, int b)
{
    printf("func1 = %d, %d\n", a, b);
}
void func2(int p, int q)
{
    printf("func2 = %d, %d\n", p, q);
}
void func3(int x, int y)
{
    printf("func3 = %d, %d\n", x, y);
}
int main()
{
    f[0] = func1;
    f[1] = func2;
    f[2] = func3;
    (*f[0])(1, 2);
    (*f[1])(3, 4);
    (*f[2])(5, 6);
    return 0;
}
```

**Output**

```cpp
func1 = 1, 2
func2 = 3, 4
func3 = 5, 6
```

## C

```cpp
4) char (*(*x())[]) ()
```

后缀:x () * [] * () char
含义:x 是返回指针数组的函数，指针数组指向返回 char 的函数

## C

```cpp
/* Example */

#include <stdio.h>
char func1() { return 'a'; }
char func2() { return 'b'; }
char func3() { return 'c'; }

char (*xarr[])() = { func1, func2, func3 };
char (*(*x())[])() { return &xarr; }

int main()
{
    printf("%c\n", ((*(x()))[0])());
    printf("%c\n", ((*(x()))[1])());
    printf("%c\n", ((*(x()))[2])());
    return 0;
}
```

**Output**

```cpp
a
b
c
```

## C

```cpp
5) char (*(*x[3])())[5]
```

后缀:x[3] * () * [5]字符
含义:x 是指向函数的 3 个指针的数组，返回指向 5 个字符数组的指针

## C

```cpp
/* Example */

#include <stdio.h>

typedef char charray5[5];

charray5 carr1 = { 'a', 'b', 'c', 'd', '\0' };
charray5 carr2 = { 'q', 'w', 'e', 'r', '\0' };
charray5 carr3 = { 'x', 'y', 'z', 'w', '\0' };

charray5* func1() { return &carr1; }
charray5* func2() { return &carr2; }
charray5* func3() { return &carr3; }

char (*(*x[3])())[5] = { func1, func2, func3 };

int main()
{
    printf("func1 = [%c, %c, %c, %c]\n",
           ((*(x[0]))())[0][0], ((*(x[0]))())[0][1],
           ((*(x[0]))())[0][2], ((*(x[0]))())[0][3]);
    printf("func2 = [%c, %c, %c, %c]\n",
           ((*(x[1]))())[0][0], ((*(x[1]))())[0][1],
           ((*(x[1]))())[0][2], ((*(x[1]))())[0][3]);
    printf("func3 = [%c, %c, %c, %c]\n",
           ((*(x[2]))())[0][0], ((*(x[2]))())[0][1],
           ((*(x[2]))())[0][2], ((*(x[2]))())[0][3]);
    return 0;
}
```

**Output**

```cpp
func1 = [a, b, c, d]
func2 = [q, w, e, r]
func3 = [x, y, z, w]
```

## C

```cpp
6) int *(*(*arr[5])()) ()
```

后缀:arr[5] * () * () * int
含义:arr 是 5 个指向函数的指针的数组返回指向函数的指针返回指向整数的指针

## C

```cpp
/* Example */

#include <stdio.h>

int a = 1;
int b = 2;
int* func1() { return &a; }
int* func2() { return &b; }

int* (*funcp1())() { return func1; }
int* (*funcp2())() { return func2; }
int* (*(*arr[5])())() = { funcp1, funcp2 };

int main()
{
    printf("%d\n", *(*(*arr[0])())());
    printf("%d\n", *(*(*arr[1])())());
    return 0;
}
```

**Output**

```cpp
1
2
```

## C

```cpp
7) void (*bsd_signal(int sig, void (*func)(int)))(int);
```

后缀:BSD _ SIG(int SIG，void(*func)(int)) * (int) void
含义:BSD _ SIG 是一个函数，它取整数&作为函数的指针(它取整数作为参数并返回 void)并返回函数的指针(它取整数作为参数并返回 void)

## C

```cpp
#include <stdio.h>

void on_sig10_exit(int u) { printf("sig10 exit\n"); }
void on_sig20_exit(int u) { printf("sig20 exit\n"); }
void default_exit(int u) { printf("default exit\n"); }
void user_default_exit(int u)
{
    printf("user default exit\n");
}

void (*exit_by)(int);

void (*bsd_signal(int sig, void (*func)(int)))(int)
{
    switch (sig) {
    case 10:
        return on_sig10_exit;
    case 20:
        return on_sig20_exit;
    default:
        if (func == NULL)
            return default_exit;
        else
            return user_default_exit;
    }
}

int main()
{
    (bsd_signal(10, NULL))(0);
    (bsd_signal(20, NULL))(0);
    (bsd_signal(30, NULL))(0);
    (bsd_signal(30, user_default_exit))(0);
    return 0;
}
```

**Output**

```cpp
sig10 exit
sig20 exit
default exit
user default exit
```

本文由“纳伦德拉·康拉尔卡尔”编辑，GeeksforGeeks 团队审核。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。