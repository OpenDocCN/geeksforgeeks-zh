# 使用 malloc()

后不释放内存会怎样

> 原文:[https://www . geesforgeks . org/当你使用 malloc/](https://www.geeksforgeeks.org/what-happens-when-you-dont-free-memory-after-using-malloc/) 后不释放内存时会发生什么

**先决条件:**[C 中的动态内存分配](https://www.geeksforgeeks.org/dynamic-memory-allocation-in-c-using-malloc-calloc-free-and-realloc/)
使用“malloc”或“内存分配”方法来动态分配指定大小的单个大内存块。它返回一个 void 类型的指针，该指针可以转换成任何形式的指针。它用默认垃圾值初始化每个块。
**语法:**

```cpp
ptr = (cast-type*) malloc(byte-size)
```

**例如:**

> ptr =(int *)malloc(100 * sizeof(int))；
> 由于 int 的大小是 4 字节，这个语句将分配 **400 字节**的内存。并且，指针 **ptr** 保存分配的存储器中第一个字节的地址。

但是使用 [malloc()](https://www.geeksforgeeks.org/dynamic-memory-allocation-in-c-using-malloc-calloc-free-and-realloc/) 的内存分配不会自行取消。所以，“ [free()](https://www.geeksforgeeks.org/g-fact-30/) ”方法被用来去分配内存。但是**免费()**方法并不是强制使用的。如果程序中没有使用 **free()** ，则在程序执行完成后，使用 **malloc()** 分配的内存将被取消分配(包含的程序执行时间相对较短，程序正常结束)。尽管如此，使用 **malloc()** :
后**自由()**还是有一些重要原因的

*   在 malloc 之后使用 free 是一种很好的编程实践。
*   有一些程序，比如数字钟，一个在后台运行很长时间的监听器，也有这样的程序定期分配内存。在这些情况下，即使是很小的存储块加起来也会产生问题。因此，我们的可用空间减少了。这也叫“内存泄漏”。如果没有在正确的时间取消内存分配，我们的系统也可能会出现内存不足的情况。

因此， **free()** 函数的使用取决于程序的类型，但建议避免不必要的内存问题，如内存泄漏。
下面是说明使用 **free()** 和 **malloc()** :
的程序

## C

```cpp
// C program to illustrate free()
// and malloc() function
#include <stdio.h>
#include <stdlib.h>

// Driver Code
int main()
{

    // Pointer to hold base address
    // of memory block
    int* p;
    int n, i;

    // Number of element
    n = 3;

    // Dynamically allocate memory
    // using malloc()
    p = (int*)malloc(n * sizeof(int));

    // Check if memory allocation is
    // successful or not.
    if (p == NULL) {
        printf("Memory allocation"
               " failed.\n");
        exit(0);
    }

    else {

        // Memory allocation successful
        printf("Memory allocation "
               "successful using"
               " malloc.\n");

        // Insert element in array
        for (i = 0; i < n; i++) {
            p[i] = i + 2;
        }

        // Print the array element
        printf("The array elements"
               " are:\n");

        for (i = 0; i < n; i++) {
            printf("%d ", p[i]);
        }

        // De-allocate the allocated
        // memory using free()
        free(p);
    }

    return 0;
}
```

**Output**

```cpp
Memory allocation successful using malloc.
The array elements are:
2 3 4 
```