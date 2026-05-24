# 在 C/C++ 中执行 main()–场景后面

> 原文:[https://www . geesforgeks . org/executing-main-in-c-幕后/](https://www.geeksforgeeks.org/executing-main-in-c-behind-the-scene/)

没有 main()函数如何编写 C 程序打印“Hello world”？
*起初，执行一个没有 **main()** 函数的程序似乎不切实际，因为 **main()** 函数是任何程序的入口点。*

让我们先了解在 Linux 系统中执行 C 程序时，引擎盖下发生了什么，main()是如何被调用的，没有 main()的程序是如何执行的。

演示时考虑以下设置。

*   Ubuntu 16.4 LTS 操作系统
*   GCC 5.4.0 编译器
*   objdump 实用程序

从 C/C++ 编程角度来看，程序入口点是 main()函数。然而，从程序执行的角度来看，它不是。在执行流程到达 main()之前，很少调用其他函数，这些函数设置参数，为程序执行准备环境变量等。

C 源代码编译后创建的可执行文件是[可执行可链接格式(ELF)文件](https://en.wikipedia.org/wiki/Executable_and_Linkable_Format)。
每个 ELF 文件都有一个 ELF 头，其中有一个 **e_entry** 字段，包含程序内存地址，可执行文件将从该地址开始执行。该内存地址指向 **_start()** 功能。
加载程序后，加载程序从 ELF 文件头中查找 **e_entry** 字段。[可执行和可链接格式(ELF)](https://en.wikipedia.org/wiki/Executable_and_Linkable_Format) 是 UNIX 系统中用于可执行文件、目标代码、共享库和核心转储的通用标准文件格式。

让我们用一个例子来看看这个。我正在创建一个**示例. c** 文件来演示这一点。

```cpp
int main()
{
   return(0);
}
```

现在使用以下命令编译它

```cpp
gcc -o example example.c

```

现在创建了一个**示例**可执行文件，让我们使用 objdump 工具来检查它

```cpp
objdump -f example

```

这将在我的机器上输出以下可执行文件的关键信息。看看下面的起始地址，这是指向 _start()函数的地址。

```cpp
example:     file format elf64-x86-64
architecture: i386:x86-64, flags 0x00000112:
EXEC_P, HAS_SYMS, D_PAGED
start address 0x00000000004003e0

```

我们可以通过解汇编可执行文件来交叉检查这个地址，输出很长，所以我只是粘贴显示这个地址 **0x00000000004003e0** 指向的输出

```cpp
objdump --disassemble  example

```

输出:

```cpp
00000000004003e0 <_start>:
  4003e0:    31 ed                    xor    %ebp,%ebp
  4003e2:    49 89 d1                 mov    %rdx,%r9
  4003e5:    5e                       pop    %rsi
  4003e6:    48 89 e2                 mov    %rsp,%rdx
  4003e9:    48 83 e4 f0              and    $0xfffffffffffffff0,%rsp
  4003ed:    50                       push   %rax
  4003ee:    54                       push   %rsp
  4003ef:    49 c7 c0 60 05 40 00     mov    $0x400560,%r8
  4003f6:    48 c7 c1 f0 04 40 00     mov    $0x4004f0,%rcx
  4003fd:    48 c7 c7 d6 04 40 00     mov    $0x4004d6,%rdi
  400404:    e8 b7 ff ff ff           callq  4003c0 
  400409:    f4                       hlt    
  40040a:    66 0f 1f 44 00 00        nopw   0x0(%rax,%rax,1)

```

我们可以清楚地看到，这是指向 _start()函数的。

### _start()函数的作用

函数的作用是:为下一个被调用的函数 **_libc_start_main()** 准备输入参数。这是 **_libc_start_main()** 功能的原型。这里我们可以看到由 _start()函数准备的参数。

```cpp
int __libc_start_main(int (*main) (int, char * *, char * *), /* address of main function*/
int argc, /* number of command line args*/
char ** ubp_av, /* command line arg array*/
void (*init) (void), /* address of init function*/
void (*fini) (void), /* address of fini function*/
void (*rtld_fini) (void), /* address of dynamic linker fini function */
void (* stack_end) /* end of the stack address*/
);
```

### _libc_start_main()函数的作用

libc_start_main()函数的作用如下–

*   为程序执行准备环境变量
*   调用 **_init()** 函数，该函数在 main()函数开始之前执行初始化。
*   Register **_fini()** and **_rtld_fini()** functions to perform cleanup after program terminates

    ### 编写不带 main()的程序

    现在我们知道如何调用 main()了。为了清楚起见，main()只不过是启动代码的一个约定术语。我们可以给启动代码起任何名字，它不一定非得是“main”。As _start()函数默认调用 main()，如果我们想执行自定义的启动代码，我们必须更改它。我们可以重写 _start()函数，让它调用我们的自定义启动代码而不是 main()。举个例子，保存为**nomin . c**–

    ```cpp
    #include<stdio.h>
    #include<stdlib.h>
    void _start()
    {
        int x = my_fun(); //calling custom main function
        exit(x);
    }

    int my_fun() // our custom main function
    {
        printf("Hello world!\n");
        return 0;
    }
    ```

    现在我们必须强制编译器不要使用它自己的 _start()实现。在 GCC 中，我们可以使用**-nostartfile**来实现

    ```cpp
    gcc -nostartfiles -o nomain nomain.c

    ```

    执行可执行文件

    ```cpp
    ./nomain

    ```

    输出:

    ```cpp
    Hello world!

    ```

    **参考文献**

    *   [http://DBP-consulting . com/教程/调试/linuxProgramStartup.html](http://dbp-consulting.com/tutorials/debugging/linuxProgramStartup.html)
    *   米兰·斯蒂凡诺维奇的高级 C/C++ 编译

    本文由 **[阿图尔·库马尔](https://www.facebook.com/atul.kr.007)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。