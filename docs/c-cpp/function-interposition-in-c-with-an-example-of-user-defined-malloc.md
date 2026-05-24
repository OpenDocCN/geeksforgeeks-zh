# 用用户定义的 malloc()示例在 C 中插入函数

> 原文:[https://www . geesforgeks . org/function-interposition-in-c-with-example-user-defined-malloc/](https://www.geeksforgeeks.org/function-interposition-in-c-with-an-example-of-user-defined-malloc/)

函数插入是用对用户定义包装器的调用替换对动态库中函数的调用的概念。

**有哪些应用？**

1.  我们可以计算函数调用的次数。
2.  存储调用方的信息和传递给函数的参数，以跟踪使用情况。
3.  检测内存泄漏，我们可以覆盖 malloc()并跟踪分配的空间。
4.  我们可以添加自己的安全策略。例如，我们可以添加一个策略，该策略不能在超过指定递归深度的情况下调用 fork。

**如何做功能介入？**
任务是编写我们自己的 malloc()，并确保我们自己的 malloc()被称为库 malloc()的 inplace。下面是一个测试不同类型的 malloc()插入的驱动程序。

```cpp
// File Name : hello.c

#include <stdio.h>
#include <stdlib.h>
#include <malloc.h>

int main(void)
{
    // Call to user defined malloc
    void *ptr = malloc(4);

    printf("Hello World\n");
    return 0;
}
```

1.  **Compile time :** Replace library call with our own function when the source code is compiled.

    ```cpp
    /* Compile-time interposition of malloc using C preprocessor. 
       A local malloc.h file defines malloc as wrapper */

    // A file that contains our own malloc function
    // File Name : mymalloc.c
    #include <stdio.h>
    #include <malloc.h>
    void *mymalloc(size_t s)
    {
       printf("My malloc called");
       return NULL;
    }
    ```

    ```cpp
    // filename : malloc.h
    // To replace all calls to malloc with mymalloc
    #define malloc(size) mymalloc(size)
    void *mymalloc(size_t size);
    ```

    在 Linux 上执行上述步骤:

    ```cpp
    // Compile the file containing user defined malloc()
    :~$ gcc  -c mymalloc.c

    // Compile hello.c with output file name as helloc. 
    // -I. is used to include current folder (.) for header
    // files to make sure our malloc.h is becomes available.
    :~$ gcc  -I. -o helloc hello.c mymalloc.o

    // Run the generated executable
    :~$ ./helloc
    My malloc called
    Hello World 
    ```

    。

2.  **Link time :** When the relocatable object files are statically linked to form an executable object file.

    ```cpp
    // filename : mymalloc.c
    /* Link-time interposition of malloc using the
       static linker’s (ld) "--wrap symbol" flag. */
    #include <stdio.h>

    // __real_malloc() is used to called actual library
    // malloc()
    void *__real_malloc(size_t size);

    // User defined wrapper for malloc()
    void *__wrap_malloc(size_t size)
    {
       printf("My malloc called");
       return NULL;
    }
    ```

    在 Linux 上执行上述步骤:

    ```cpp
    // Compile the file containing user defined malloc()
    :~$ gcc  -c mymalloc.c

    // Compile hello.c with output name as hellol  
    // "-Wl,--wrap=malloc" is used tell the linker to use
    //  malloc() to call __wrap_malloc(). And to use 
    // __real_malloc() to actual library malloc() 
    :~$ gcc  -Wl,--wrap=malloc -o hellol hello.c mymalloc.o

    // Run the generated executable
    :~$ ./hellol
    My malloc called
    Hello World 
    ```

    。

3.  **Load/run time :** When an executable object file is loaded into memory, dynamically linked, and then executed.

    环境变量 **LD_PRELOAD** 给加载程序一个要在命令或可执行文件之前加载的库的列表。
    我们创建了一个动态库，并确保它在 hello.c .的可执行文件之前被加载

    ```cpp
    /* Run-time interposition of malloc based on dynamic linker’s
       (ld-linux.so) LD_PRELOAD mechanism */
    #define _GNU_SOURCE
    #include <stdio.h>

    void *malloc(size_t s)
    {
       printf("My malloc called\n");
       return NULL;
    }
    ```

    在 Linux 上执行上述步骤:

    ```cpp

    // Compile hello.c with output name as helloc
    :~$ gcc -o hellor hello.c

    // Generate a shared library myalloc.so. Refer
    // https://www.geeksforgeeks.org/working-with-shared-libraries-set-2/
    // for details.
    :~$ gcc -shared -fPIC -o mymalloc.so mymalloc.c

    // Make sure shared library is loaded and run before .
    :~$ LD_PRELOAD=./mymalloc.so ./hellor
    My malloc called
    Hello World

    ```

    。

    为了更好的可读性，用户定义的 malloc 的代码保持较小。理想情况下，它应该通过调用库 malloc()来分配内存。

    **来源:**
    [https://www . utdallas . edu/~ zxl 111930/spring 2012/public/lec18-讲义. pdf](https://www.utdallas.edu/~zxl111930/spring2012/public/lec18-handout.pdf)

    本文由**阿迪亚查特吉**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论