# C 程序删除一个文件

> 原文:[https://www.geeksforgeeks.org/c-program-delete-file/](https://www.geeksforgeeks.org/c-program-delete-file/)

C/C++ 中的[删除](http://www.cplusplus.com/reference/cstdio/remove/)功能可以用来删除文件。如果成功删除文件，函数返回 0，否则返回非零值。

```cpp
#include<stdio.h>

int main()
{
   if (remove("abc.txt") == 0)
      printf("Deleted successfully");
   else
      printf("Unable to delete the file");

   return 0;
}
```

利用 C 语言中的 remove()函数，我们可以编写一个程序，在编译执行后可以自行销毁。

**说明:**这可以使用 c 中的[移除功能](https://www.geeksforgeeks.org/c-program-delete-file/)来完成，注意，这是在 Linux 环境下完成的。因此，remove 函数被输入命令行参数中的第一个参数，即编译后创建的 **a.out** 文件(可执行文件)。因此程序将被销毁。

```cpp
#include<stdio.h>
#include<stdlib.h>

int main(int c, char *argv[])
{
    printf("By the time you will compile me I will be destroyed \n");

   // array of pointers to command line arguments
    remove(argv[0]);    

  // Note: argv[0] will contain the executable file i.e. 'a.out'

return 0;
}

// This code is contributed by  MAZHAR IMAM KHAN.
```

输出:

```cpp
By the time you will compile me I will be destroyed

```

上述输出后， **a.out** 文件将被删除。

如发现任何不正确的地方，请写评论，或者你想分享更多关于上述话题的信息