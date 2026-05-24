# 悬空指针和空指针的区别

> 原文:[https://www . geesforgeks . org/悬空指针和空指针的区别/](https://www.geeksforgeeks.org/difference-between-dangling-pointer-and-void-pointer/)

[**悬空指针**](https://www.geeksforgeeks.org/dangling-void-null-wild-pointers/) **:** 指向已被删除(或释放)的内存位置的[指针称为悬空指针。有三种不同的方式将指针作为悬空指针:](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)

[](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)
*   [](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)[By releasing memory](https://www.geeksforgeeks.org/how-to-deallocate-memory-without-using-free-in-c/)
*   [Function call](https://www.geeksforgeeks.org/what-happens-when-we-call-a-function/)
*   When the variable is out of range

[**Void 指针**](https://www.geeksforgeeks.org/void-pointer-c-cpp/) **:** Void 指针是一种特定的指针类型–Void *–一种指向存储中某个数据位置的[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)，它没有任何特定的类型。Void 指的是类型。基本上，它指向的数据类型可以是任何类型。如果我们将地址[字符数据类型](https://www.geeksforgeeks.org/data-types-in-java/)分配给一个空指针，它将变成一个字符指针，如果是 int 数据类型，那么就是 int 指针，依此类推。任何指针类型都可以转换为空指针。因此，它可以指向任何值。以下是关于空指针的一些要点:

*   Empty pointer **cannot be dereferenced** . However, the [type can be used to cast the](https://www.geeksforgeeks.org/typecasting-in-c/) empty pointer.
*   [Pointer algorithm](https://www.geeksforgeeks.org/pointer-arithmetics-in-c-with-examples/) to complete, because of the lack of specific value and size.

**<u>悬空指针与空指针的表格区别</u>:**

<figure class="table">

| **悬空指针** | **空指针** |
| A dangling pointer is a pointer that occurs when an object is deallocated from memory without modifying the pointer value. | A null pointer is a pointer that can point to any data type. |
| It points to the deleted [object](https://www.geeksforgeeks.org/c-classes-and-objects/) . | A void pointer can assign an address of any data type. |
| It usually happens when [objects destroy](https://www.geeksforgeeks.org/exception-handling-and-object-destruction-in-c-set-1/) . | Pointers to null have the same representation as pointers of character type. |
| The dangling pointer error can only be avoided by initializing the pointer to a NULL value. | An empty pointer can store any type of object. |
| The floating pointer will be used in conjunction with the [free ()](https://www.geeksforgeeks.org/dynamic-memory-allocation-in-c-using-malloc-calloc-free-and-realloc/) function in [c](https://www.geeksforgeeks.org/c-language-set-1-introduction/) . | Also called universal pointer. |

</figure>