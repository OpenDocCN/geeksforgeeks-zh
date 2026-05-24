# 分段故障(SIGSEGV)与总线错误(SIGBUS)

> 原文:[https://www . geesforgeks . org/segmentation-fault-sigsegv-vs-bus-error-sigbus/](https://www.geeksforgeeks.org/segmentation-fault-sigsegv-vs-bus-error-sigbus/)

**分段故障(SIGSEGV)** 和**总线错误(SIGBUS)** 是当操作系统检测到严重的程序错误并且由于这些错误程序不可能继续执行时产生的信号。
**1)** [**分段故障**](https://www.geeksforgeeks.org/core-dump-segmentation-fault-c-cpp/) (也称为 SIGSEGV，通常是信号 11)发生在程序试图在分配给它的内存之外进行写/读操作时，或者在写入只能读取的内存时。换句话说，当程序试图访问它无法访问的内存时。SIGSEGV 是“分段违规”的缩写。
产生 SIGSEGV 信号的少数情况如下:
- >使用未初始化的指针
- >去引用空指针
- >试图访问程序不拥有的内存(例如试图访问数组边界外的数组元素
)。
- >尝试访问已经取消分配的内存(尝试使用悬空指针)。
举例请参考[这篇](https://www.geeksforgeeks.org/core-dump-segmentation-fault-c-cpp/)文章。
**2)** [**总线错误**](https://en.wikipedia.org/wiki/Bus_error) (也称为 SIGBUS，通常是信号 10)发生在进程试图访问 CPU 无法物理寻址的内存时。换句话说，程序试图访问的内存不是有效的内存地址。这是由于中央处理器的对齐问题造成的(例如，试图从不是 4 的倍数的地址读取一个长的)。SIGBUS 是“总线错误”的缩写。
SIGBUS 信号出现在以下情况下，
- >程序指令 CPU 读取或写入无效的特定物理内存地址/请求的物理地址无法被整个计算机系统识别。
- >内存的未对齐访问(例如，如果多字节访问必须 16 位对齐，则 0、2、4、6 等处的地址(以字节为单位)将被视为对齐，因此可以访问，而地址 1、3、5 等将被视为未对齐。)
**分段故障和总线错误的主要区别**是分段故障表示对有效内存的无效访问，而总线错误表示对无效地址的访问。
以下是取自[维基百科](https://en.wikipedia.org/wiki/Bus_error)的总线错误示例。

## C

```cpp
// C program to demonstrate Bus Error
#include <stdlib.h>

int main(int argc, char **argv)
{

#if defined(__GNUC__)
# if defined(__i386__)
    /* Enable Alignment Checking on x86 */
    __asm__("pushf\norl $0x40000,(%esp)\npopf");
# elif defined(__x86_64__)
     /* Enable Alignment Checking on x86_64 */
    __asm__("pushf\norl $0x40000,(%rsp)\npopf");
# endif
#endif

    /* malloc() always provides aligned memory */
    char *cptr = malloc(sizeof(int) + 1);

    /* Increment the pointer by one, making it
       misaligned */
    int *iptr = (int *) ++ cptr;

    /* Dereference it as an int pointer, causing
       an unaligned access */
    *iptr = 42;

    /* Following accesses will also result in
       sigbus error.
       short *sptr;
       int    i;

       sptr = (short *)&i;

       // For all odd value increments, it will
       // result in sigbus.
       sptr = (short *)(((char *)sptr) + 1);
       *sptr = 100;    */

    return 0;
}
```

输出:

```cpp
Bad memory access (SIGBUS) 
```

本文由**普拉山·庞格拉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。