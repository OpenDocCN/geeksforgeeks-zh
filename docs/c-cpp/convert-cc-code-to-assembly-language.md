# 将 C/C++ 代码转换为汇编语言

> 原文:[https://www . geesforgeks . org/convert-cc-code-to-assembly-language/](https://www.geeksforgeeks.org/convert-cc-code-to-assembly-language/)

我们使用 g++ 编译器将提供的 C 代码转换成汇编语言。要查看 C 编译器生成的汇编代码，我们可以使用命令行上的**-【S】**选项:

**语法:**

```cpp
$ gcc -S filename.c
```

这将导致 gcc 运行编译器，生成一个程序集文件。假设我们编写一个 C 代码，并将其存储在一个名为“geeks.c”的文件中。

## C

```cpp
// C code stored in geeks.c file
#include <stdio.h>

// global string
char s[] = "GeeksforGeeks";

// Driver Code
int main()
{
    // Declaring variables
    int a = 2000, b =17;

    // Printing statement
    printf("%s %d \n", s, a+b);
}
```

**运行命令:**

```cpp
$ gcc -S geeks.c
```

这将导致 gcc 运行编译器，生成一个汇编文件 **geeks.s** ，并且不再进一步。(通常它会调用汇编程序来生成目标代码文件。)
汇编代码文件包含各种声明，包括一组行:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
    .section    __TEXT, __text, regular, pure_instructions
    .macosx_version_min 10, 12
    .global    _main
    .align    4, 0x90
_main:                                  ## @main
    .cfi_startproc
## BB#0:
    pushq    %rbp
Ltmp0:
    .cfi_def_cfa_offset 16
Ltmp1:
    .cfi_offset %rbp, -16
    movq    %rsp, %rbp
Ltmp2:
    .cfi_def_cfa_register %rbp
    subq    $16, %rsp
    leaq    L_.str(%rip), %rdi
    leaq    _s(%rip), %rsi
    movl    $2000, -4(%rbp)         ## imm = 0x7D0
    movl    $17, -8(%rbp)
    movl    -4(%rbp), %eax
    addl    -8(%rbp), %eax
    movl    %eax, %edx
    movb    $0, %al
    callq    _printf
    xorl    %edx, %edx
    movl    %eax, -12(%rbp)         ## 4-byte Spill
    movl    %edx, %eax
    addq    $16, %rsp
    popq    %rbp
    retq
    .cfi_endproc

    .section    __DATA, __data
    .global    _s                      ## @s
_s:
    .asciz    "GeeksforGeeks"

    .section    __TEXT, __cstring, cstring_literals
L_.str:                                 ## @.str
    .asciz    "%s %d \n"

.subsections_via_symbols
```

上面代码中的每一行缩进对应一条机器指令。例如 **pushq** 指令指示寄存器 **%rbp** 的内容应该被推送到程序栈上。所有关于局部变量名或数据类型的信息都被删除了。我们仍然看到对全局变量
的引用，因为编译器还没有确定这个变量将存储在内存的什么位置。
本文由 [**Sahil Rajput**](https://www.linkedin.com/in/sahil-rajput-3ba2b3134/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。