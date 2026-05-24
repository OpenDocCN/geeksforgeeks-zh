# 删除并释放 C++ 中的()

> 原文:[https://www.geeksforgeeks.org/delete-and-free-in-cpp/](https://www.geeksforgeeks.org/delete-and-free-in-cpp/)

**删除**和 **free()** 在编程语言中具有相似的功能，但它们不同。在 C++ 中，删除操作符应该只用于指向使用新操作符分配的内存的指针或空指针，而 free()应该只用于指向使用 malloc()分配的内存的指针或空指针。

**delete 和 free 的区别有:**

<figure class="table">

| 

delete()

 | 

free()

 |
| --- | --- |
| It is an operator. | It is a library function. |
| Dynamically deallocate memory. | It destroys memory at run time. |
| It should only be used as a pointer to the memory allocated by the new operator of **, or as a null pointer.** | It should only be used as a pointer or null pointer to the memory allocated using **malloc ()** . |
| This operator calls the destructor after it destroys the allocated memory. | This function only releases memory from the heap. It does not call the destructor. |
| It's faster. | It is a feature that is relatively slower than deleting. |

</figure>

> **注意:【free()不应该用于取消分配使用 **new** 分配的内存的最重要原因是，它不调用该对象的析构函数，而 delete 运算符调用。**

**删除运算符示例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate the correct and incorrect
// usage of delete operator
#include <cstdlib>
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int x;
    int* ptr1 = &x;
    int* ptr2 = (int*)malloc(sizeof(int));
    int* ptr3 = new int;
    int* ptr4 = NULL;

    // delete Should NOT be used like below because x is
    // allocated on stack frame
    delete ptr1;

    // delete Should NOT be used like below because x is
    // allocated using malloc()
    delete ptr2;

    // Correct uses of delete
    delete ptr3;
    delete ptr4;

    getchar();
    return 0;
}
```

【free()函数示例:

## C++

```cpp
// CPP program to demonstrate the correct and incorrect
// usage of free() function
#include <cstdlib>
#include <iostream>
using namespace std;

// Driver Code
int main()
{

    int* ptr1 = NULL;
    int* ptr2;
    int x = 5;
    ptr2 = &x;
    int* ptr3 = (int*)malloc(5 * sizeof(int));

    // Correct uses of free()
    free(ptr1);
    free(ptr3);

    // Incorrect use of free()
    free(ptr2);

    return 0;
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。