# malloc()和 calloc()的区别，示例

> 原文:[https://www . geeksforgeeks . org/malloc-and-calloc-with-examples/](https://www.geeksforgeeks.org/difference-between-malloc-and-calloc-with-examples/)

**先决条件:** [使用 malloc()、calloc()、free()和 realloc()](https://www.geeksforgeeks.org/dynamic-memory-allocation-in-c-using-malloc-calloc-free-and-realloc/) 在 C 中进行动态内存分配

名称 **malloc** 和 **calloc()** 是动态分配内存的库函数。这意味着在运行时(程序执行)从堆段中分配内存。

*   **Initialization:** malloc() allocates memory block of given size (in bytes) and returns a pointer to the beginning of the block. malloc() doesn’t initialize the allocated memory. If we try to access the content of memory block(before initializing) then we’ll get segmentation fault error(or maybe garbage values).

    ```cpp
    void* malloc(size_t size);
    ```

    calloc()分配内存，并将分配的内存块初始化为零。如果我们试图访问这些块的内容，那么我们将得到 0。

    ```cpp
    void* calloc(size_t num, size_t size);
    ```

*   **参数数量:**与 malloc()不同，calloc()采用两个参数:
    1)要分配的块数。
    2)每个区块的大小。
*   **Return Value:** After successful allocation in malloc() and calloc(), a pointer to the block of memory is returned otherwise **NULL** value is returned which indicates the failure of allocation.

    例如，如果我们想为 5 个整数的数组分配内存，请参见以下程序:-

    ```cpp
    // C program to demonstrate the use of calloc()
    // and malloc()
    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {
        int* arr;

        // malloc() allocate the memory for 5 integers
        // containing garbage values
        arr = (int*)malloc(5 * sizeof(int)); // 5*4bytes = 20 bytes

        // Deallocates memory previously allocated by malloc() function
        free(arr);

        // calloc() allocate the memory for 5 integers and
        // set 0 to all of them
        arr = (int*)calloc(5, sizeof(int));

        // Deallocates memory previously allocated by calloc() function
        free(arr);

        return (0);
    }
    ```

    *我们可以通过使用 malloc()后跟 memset()，*来实现与 calloc()相同的功能

    ```cpp
    ptr = malloc(size);
    memset(ptr, 0, size);
    ```

    > **注意:*最好使用 malloc 而不是 calloc，除非我们想要零初始化，因为 malloc 比 calloc 快。因此，如果我们只想复制一些东西，或者做一些不需要用零填充块的事情，那么 malloc 将是一个更好的选择。*T3】**

    本文由 [Shubham Bansal](https://www.quora.com/profile/Shubham-Bansal-209) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。