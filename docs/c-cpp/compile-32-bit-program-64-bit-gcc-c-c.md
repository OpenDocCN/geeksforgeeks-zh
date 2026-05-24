# 如何用 C 和 C++

在 64 位 gcc 上编译 32 位程序

> 原文:[https://www . geesforgeks . org/compile-32 位程序-64 位-gcc-c-c/](https://www.geeksforgeeks.org/compile-32-bit-program-64-bit-gcc-c-c/)

大多是 C 和 C++ 的编译器(gcc 或者 clang)，现在都自带默认的 **64 位**版本。就速度而言，这是个不错的选择。但是，如果有人为了测试或调试的目的，想用 32 位的**而不是 64 位的**来运行他们的程序，这就会导致问题。因此，我们必须对此有所了解。
在继续之前，让我们确认一下当前系统中安装的是哪个位版本的 **gcc** 。
只需在 Linux 终端上键入以下命令。**** 

```cpp
****Command**: gcc -v
**Output** 
Using built-in specs.
COLLECT_GCC=gcc
COLLECT_LTO_WRAPPER=/usr/lib/gcc/x86_64-linux-gnu/5/lto-wrapper
Target: x86_64-linux-gnu
......................
......................**
```

****因此第四行 *Target: x86_64-linux-gnu* 确认我们正在运行 64 位 gcc。
现在为了用 32 位 gcc 编译，只需在编译‘C’语言程序的命令行中添加一个标志 **-m32** 。例如，要通过 Linux 终端编译 **geek.c** 的文件，必须用 **-m32** 标志编写以下命令。**** 

```cpp
****Command:** gcc -m32 geek.c -o geek**
```

****如果出现如下错误:**** 

```cpp
**fatal error: bits/predefs.h: No such file or directory**
```

****那么它表明 gcc 的标准库丢失了。在这种情况下，您必须使用以下命令来安装**gcc-multlib**:**** 

```cpp
**For C language:
sudo apt-get install gcc-multilib
For C++ language:
sudo apt-get install g++-multilib**
```

****之后，您将能够在 64 位系统上编译 32 位二进制文件。
**添加“-m32”标志后如何检查程序是否用 32 位编译？**
嗯，我们可以通过下面的程序很容易地检查这一点。**** 

## ****卡片打印处理机（Card Print Processor 的缩写）****

```cpp
**// C program to demonstrate difference
// in output in 32-bit and 64-bit gcc
// File name: geek.c
#include<stdio.h>
int main()
{
    printf("Size = %lu", sizeof(size_t));
}**
```

****用这两个不同的命令在 Linux 中编译上述程序，
默认 64 位编译，**** 

```cpp
****Input:** gcc -m64 geek.c -o out
**Output:** ./out
Size = 8**
```

****强制 32 位编译，**** 

```cpp
****Input:** gcc -m32 geek.c -o out
**Output:** ./out
Size = 4**
```

****我们能从上面的程序中得出什么结论吗？也许是的，让我们试着了解更多。
由于像**长、** [**大小 _t**](https://www.geeksforgeeks.org/size_t-data-type-c-language/) **这样的数据类型的大小、指针数据类型(int*、char*等)**是依赖于编译器的，因此它会根据编译器的位生成不同的输出。
本文由[舒巴姆·班萨尔](https://www.quora.com/profile/Shubham-Bansal-209)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。****