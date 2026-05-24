# C 中的自毁代码

> 原文:[https://www.geeksforgeeks.org/self-destructing-code-c/](https://www.geeksforgeeks.org/self-destructing-code-c/)

使用 C 语言中的 remove()函数，我们可以编写一个程序，在编译和执行后可以自我销毁。

**说明:**这可以使用 c 中的[移除功能](https://www.geeksforgeeks.org/c-program-delete-file/)来完成，注意，这是在 Linux 环境下完成的。因此，remove 函数被输入命令行参数中的第一个参数，即编译后创建的 **a.out** 文件(可执行文件)。因此程序将被销毁。

```cpp
// CPP program of self destructing output file
#include<stdio.h>
#include<stdlib.h>

int main(int c, char *argv[])
{
    printf("By the time you run me "
           "I will be destroyed \n");

    // Array of pointers to command line arguments
    remove(argv[0]);    

    // Note: argv[0] will contain the executable\
    // file i.e. 'a.out'

    return 0;
}
```

步骤:

1.  打开终端。
2.  在终端上输入以下命令:

    ```cpp
     gcc self.c 
    ```

3.  这将创建*输出*文件。
4.  在终端上输入以下命令:

    ```cpp
     ./a.out 
    ```

输出:

```cpp
By the time you run me, I will be destroyed

```

上述输出后， **a.out** 文件将被删除。因此我们的工作完成了。
T3】