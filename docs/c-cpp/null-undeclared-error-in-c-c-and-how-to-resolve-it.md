# C/c++ 中 NULL 未声明错误及如何解决

> 原文:[https://www . geesforgeks . org/null-未声明-c-c 中的错误以及如何解决它/](https://www.geeksforgeeks.org/null-undeclared-error-in-c-c-and-how-to-resolve-it/)

**什么是未声明的错误:**
当我们在程序中使用一些**常量**时，它们可能是内置常量，用户可以根据需要创建。但是当我们使用一些常量，它们不是内置的，也不是用户定义的，在这种情况下，我们会得到一个未声明的错误。

下面是显示**空**未声明错误示例的代码:

```cpp
using namespace std;

// Driver Code
int main()
{
    // NULL declared
    int* num = NULL;
    return 0;
}
```

上述代码将显示一个错误为**“空未声明错误”**。空未声明错误的原因是**“空”**不是内置常数。

**为什么我们需要 NULL？**
当我们在程序中创建一些指针时，它们被用来存储地址。但是一个未初始化的指针变量是非常危险的，所以我们可以给它们赋值**空**，这意味着它们不指向任何内存位置，所以我们的程序可以平稳安全地运行。
现在如果 NULL 不是内置常量我们如何克服 NULL 未声明的错误。

以下是一些用于删除空未声明错误的代码:

1.  **分配 0:** 我们可以简单地分配 **0** 而不是将**空值**分配给 num，这表明它没有指向任何地址，因此最简单的解决方案是简单地分配 0。
    下面的代码展示了它的实现:

    ```cpp
    using namespace std;

    // Driver Code
    int main()
    {
        int* num = 0;
        return 0;
    }
    ```

2.  **包含“stddef.h”头文件:**在 **stddef.h** 头文件**中已经定义了空**，所以我们可以将这个头文件包含在我们的程序中，我们的程序将毫无错误地编译和执行。
    下面的代码展示了它的实现:

    ```cpp
    #include <stddef.h>

    // Driver Code
    int main()
    {
        int* num = NULL;
        return 0;
    }
    ```

3.  **包含 iostream 头文件:**在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中，如果我们想执行我们的程序而没有空的未声明的错误，我们可以简单地将 iostream 包含在我们的程序中，并使其发生而没有任何错误。
    下面的代码展示了它的实现:

    ```cpp
    #include <iostream>
    using namespace std;

    // Driver Code
    int main()
    {
        int* num = NULL;
        return 0;
    }
    ```

4.  **#定义空 0:** 使用 T**#定义空 0** 在我们的程序中我们可以解决空未声明的错误。
    下面的代码展示了它的实现:

    ```cpp
    #define NULL 0
    using namespace std;

    // Driver Code
    int main()
    {
        int* num = NULL;
        return 0;
    }
    ```

5.  **在较新的 C++ 中(C++ 11 及更高版本):** : **nullptr** 是一个内置常量，因此我们可以使用它来代替使用 NULL。

    ```cpp
    #include <iostream>
    using namespace std;

    // Driver Code
    int main()
    {
        int* num = nullptr;
        return 0;
    }
    ```