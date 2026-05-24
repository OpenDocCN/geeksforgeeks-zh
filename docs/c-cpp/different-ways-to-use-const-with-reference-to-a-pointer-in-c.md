# 在 C++ 中引用指针使用 Const 的不同方式

> 原文:[https://www . geeksforgeeks . org/different-to-use-const-with-reference-a-pointer-in-c/](https://www.geeksforgeeks.org/different-ways-to-use-const-with-reference-to-a-pointer-in-c/)

在参考指针使用[常量](https://www.geeksforgeeks.org/const-qualifier-in-c/)之前，让我们先一个一个地看看它们是什么:

*   **[Pointers](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)** are used to store the address of variables or a memory location. A variable can be declared as a pointer by putting ‘*****’ in the declaration.

    ```cpp
    datatype *var_name; 

    ```

    **示例:**

    ```cpp
    // C++ program to
    // demonstrate a Pointer

    #include <iostream>
    using namespace std;

    int main()
    {

        // Variable
        int i = 10;

        // Pointer to i
        int* ptr_i = &i;

        cout << *ptr_i;

        return 0;
    }
    ```

    **Output:**

    ```cpp
    10

    ```

*   **[Reference](https://www.geeksforgeeks.org/references-in-c/)**: When a variable is declared as a reference, it becomes an alternative name for an existing variable. A variable can be declared as a reference by putting ‘**&**’ in the declaration.

    ```cpp
    datatype &var_name; 

    ```

    **示例:**

    ```cpp
    // C++ program to
    // demonstrate a Reference

    #include <iostream>
    using namespace std;

    int main()
    {

        // Variable
        int i = 10;

        // Reference to i.
        int& ref = i;

        // Value of i is now
        // changed to 20
        ref = 20;

        cout << i;

        return 0;
    }
    ```

    **Output:**

    ```cpp
    20

    ```

*   **[References to pointers](https://www.geeksforgeeks.org/reference-to-a-pointer-in-c-with-examples-and-applications/)** is a modifiable value that’s used same as a normal pointer.

    ```cpp
    datatype *&var_name; 

    ```

    **例 1:**

    ```cpp
    // C++ program to demonstrate
    // References to pointers

    #include <iostream>
    using namespace std;

    int main()
    {

        // Variable
        int i = 10;

        // Pointer to i
        int* ptr_i = &i;

        // Reference to a Pointer ptr_i
        int*& ptr_ref = ptr_i;

        cout << *ptr_ref;

        return 0;
    }
    ```

    **Output:**

    ```cpp
    10

    ```

    这里 **ptr_ref** 是对指向变量“I”的指针 **ptr_i** 的*引用。因此，ptr_ref 处的打印值给出了“I”的值，即 10。*

    **示例 2:** 现在让我们尝试更改由指针引用表示的地址

    ```cpp
    // C++ program to demonstrate
    // References to pointers

    #include <iostream>
    using namespace std;

    int main()
    {

        // Variable
        int i = 10;
        int j = 5;

        // Pointer to i
        int* ptr = &i;

        // Reference to a Pointer ptr
        int*& ptr_ref = ptr;

        // Trying to change the reference
        // to Pointer ptr_ref to address of j
        ptr_ref = &j;

        cout << *ptr;

        return 0;
    }
    ```

    **Output:**

    ```cpp
    5

    ```

    这里它输出 5，因为 j 的值是 5，我们把 ptr_ref 改为指向 j。现在由于 ptr_ref 是指针 ptr 的引用，ptr 现在指向 j。因此我们得到了预期的输出。

*   **Const Reference to a pointer** is a non-modifiable value that’s used same as a const pointer.

    ```cpp
    datatype* const &var_name; 

    ```

    **例 1:**

    ```cpp
    // C++ program to demonstrate
    // References to pointers

    #include <iostream>
    using namespace std;

    int main()
    {

        // Variable
        int i = 10;
        int j = 5;

        // Pointer to i
        int* ptr = &i;

        // Const Reference to a Pointer
        int* const& ptr_ref = ptr;

        // Trying to change the const reference
        // to Pointer ptr_ref to address of j
        ptr_ref = &j;

        cout << *ptr;

        return 0;
    }
    ```

    **编译错误:**

    ```cpp
    In function 'int main()':
    prog.cpp:23:13: error: assignment of read-only reference 'ptr_ref'
         ptr_ref = &j;
                 ^

    ```

    这里我们得到一个编译时错误，因为它是指针的常量引用，因此我们不允许重新分配它。

    **例 2:**

    ```cpp
    // C++ program to demonstrate
    // References to pointers

    #include <iostream>
    using namespace std;

    int main()
    {

        // Variable
        int i = 10;
        int j = 5;

        // Pointer to i
        int* ptr = &i;

        // Const Reference to a Pointer
        int* const& ptr_ref = ptr;

        // Trying to change the reference
        // to Pointer ptr_ref
        *ptr_ref = 100;

        cout << *ptr;

        return 0;
    }
    ```

    **Output:**

    ```cpp
    100

    ```

    它打印 100，因为它不是对常量指针的引用。

    <u>**为什么示例 2 没有抛出编译时错误，而示例 1 抛出了编译时错误？**T3】</u>

    *   **在示例 1** 中， **ptr_ref** 是指向 int 的指针的常量引用，我们正在尝试更改 **ptr_ref** 的值。因此，当我们试图修改一个常量值时，编译器会抛出一个编译时错误。
    *   **在示例 2** 中， **ptr_ref** 是对指向 int 的指针的常量引用，我们正在尝试更改 ***ptr_ref** 的值，这意味着我们正在更改指针所指向的 int 的值，而不是指针的常量引用。所以编译器不会抛出任何错误，指针现在指向值 100。因此 int 在这里不是常数，但是指针是。因此，int 的值更改为 100。
*   **Reference to a Const Pointer** is a reference to a constant pointer.

    ```cpp
    datatype const *&var_name; 

    ```

    **示例:**

    ```cpp
    // C++ program to demonstrate
    // References to pointers

    #include <iostream>
    using namespace std;

    int main()
    {

        // Variable
        int i = 10;
        int j = 5;

        // Const Pointer to i
        int const* ptr = &i;

        // Reference to a Const Pointer
        int const*& ptr_ref = ptr;

        // Trying to change the value of the pointer
        // ptr with help of its reference ptr_ref
        *ptr_ref = 124;

        cout << *ptr;
        return 0;
    }
    ```

    **编译错误:**

    ```cpp
    In function 'int main()':
    prog.cpp:23:14: error: assignment of read-only location '* ptr_ref'
         *ptr_ref = 124;
                  ^

    ```

    这里我们再次得到编译时错误。这是因为这里编译器说要声明 **ptr_ref** 作为指向 const int 的指针的引用。所以我们不能改变 I 的值。