# C 中静态和动态内存分配的区别

> 原文:[https://www . geesforgeks . org/静态内存分配与动态内存分配的区别-in-c/](https://www.geeksforgeeks.org/difference-between-static-and-dynamic-memory-allocation-in-c/)

**内存分配:**内存分配是为计算机程序和服务分配物理或虚拟内存空间的过程。内存分配在程序执行之前或执行时完成。内存分配有两种类型:

1.  [编译时或静态内存分配](https://www.geeksforgeeks.org/difference-between-static-allocation-and-heap-allocation/)
2.  [运行时或动态内存分配](https://www.geeksforgeeks.org/what-is-dynamic-memory-allocation/)

**静态内存分配:**编译器为声明的变量分配静态内存。使用 运算符的 [*地址可以找到该地址，并且可以将其分配给指针。内存在编译时分配。*](https://www.geeksforgeeks.org/address-function-c-cpp/)

**动态内存分配:**执行时(运行时)完成的内存分配称为**动态内存分配**。函数 [calloc()和 malloc()](https://www.geeksforgeeks.org/dynamic-memory-allocation-in-c-using-malloc-calloc-free-and-realloc/) 支持分配动态内存。在动态分配中，当值由函数返回并分配给指针变量时，通过使用这些函数来分配内存空间。

**<u>C 中静态和动态内存分配的表格差异</u> :**

<figure class="table">

| 

### 序列号

 | 

### Static memory allocation

 | 

### Dynamic memory allocation

 |
| one | In static memory allocation, variables are permanently allocated until program execution or function call is completed. | In dynamic memory allocation, variables will only be allocated when your program unit is activated. |
| Two | Static memory allocation is completed before the program is executed. | Dynamic memory allocation is completed during program execution. |
| three | It uses [stack](https://www.geeksforgeeks.org/stack-data-structure/) to manage the static allocation of memory. | It uses [heap](https://www.geeksforgeeks.org/heap-data-structure/) to manage the dynamic allocation of memory. |
| four | It is inefficient. | It is more efficient. |
| five | In static memory allocation, there is memory reusability, and memory can be released when it is not needed. |
| six | In static memory allocation, once the memory is allocated, the memory size cannot be changed. | In dynamic memory allocation, the memory size can be changed when allocating memory. |
| seven | In this memory allocation scheme, we can't reuse unused memory. | This allows memory reuse. Users can allocate more memory when needed. In addition, users can release memory when needed. |
| eight | In this memory allocation scheme, the execution speed is faster than dynamic memory allocation. | In this memory allocation scheme, the execution speed is slower than static memory allocation. |
| nine | This memory is allocated at compile time. | This memory is allocated at run time. |
| Ten | The memory allocated here is reserved from the beginning to the end of the program. | The memory allocated here can be released at any time during the running of the program. |
| Eleven | **Example:** This static memory allocation is generally used for [array](https://www.geeksforgeeks.org/introduction-to-arrays/) . | **Example:** This dynamic memory allocation is generally used for [linked list](https://www.geeksforgeeks.org/data-structures/linked-list/) . |

</figure>