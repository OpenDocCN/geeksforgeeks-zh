# c++ 中的复制和交换习惯用法

> 原文:[https://www.geeksforgeeks.org/copy-swap-idiom-c/](https://www.geeksforgeeks.org/copy-swap-idiom-c/)

在深入讨论之前，让我们先看一下我们使用的普通“重载赋值运算符”。

```cpp
// Simple C++ program to demonstrate overloading of
// assignment operator.
#include <iostream>
#include <cstring>
using namespace std;

class anyArrayClass
{
    int size;
    int *ptr;
public:

    // Initializer list
    anyArrayClass(int s=0):size(s),
        ptr(size? new int[size]:nullptr) {}

    // Copy constructor
    anyArrayClass(const anyArrayClass& obj):size(obj.size),
        ptr(size? new int[size]:nullptr)
    {
        memmove(ptr, obj.ptr, size*sizeof(int));
    }

    // Overloaded assignment operator
    anyArrayClass& operator=(const anyArrayClass& obj)
    {
        // self assignment check
        if (this != &obj)
        {
            delete ptr;
            size = obj.size;
            ptr = size? new int[size]: nullptr;
            memmove(ptr, obj.ptr, size*sizeof(int));
            return *this;
        }
    }
    ~anyArrayClass()
    {
        delete[] ptr;
    }
}
```

上述赋值运算符执行以下操作:
1。自我分配检查。
2。如果任务不是给自己的，那么它会遵循。
a)释放分配给此- > ptr 的内存
b)分配新内存给此- > ptr 并复制值
c)返回*此

**上述方法的缺点:**

1.  自我分配检查:自我分配很少进行，因此自我分配检查在大多数情况下都不相关。这只会降低代码的速度。
2.  内存释放和分配:可以看到，首先释放内存(让指针悬空)，然后分配新的内存块。现在，如果由于某种原因内存没有被分配，并且抛出了一个异常，那么“this->ptr”将保持悬空，指向一个被释放的内存。场景应该是要么分配成功，要么对象根本不应该改变。

复制和交换方法的作用来了。这种方法很好地解决了上述问题，也为代码的重用提供了空间。让我们看看到底是什么。

考虑以下代码:

```cpp
// Simple C++ program to demonstrate use of copy-and-swap
// idiom by improving above code.
#include <iostream>
#include <cstring>
using namespace std;

class anyArrayClass
{
    int size;
    int *ptr;
public:
    anyArrayClass(int s=0):size(s),
     ptr(size? new int[size]:nullptr) {}

    // Copy constructor
    anyArrayClass(const anyArrayClass& obj):size(obj.size),
                           ptr(size? new int[size]:nullptr)
    {
        memmove(ptr, obj.ptr, size*sizeof(int));
    }

    friend void swap(anyArrayClass& obj1, anyArrayClass& obj2)
    {
        std::swap(obj1.size, obj2.size);
        std::swap(obj1.ptr, obj2.ptr);
    }

    // overloaded assignment operator
    // argument passed by value. calls copy ctor
    anyArrayClass& operator=(anyArrayClass obj)    
    {
        // calling friend function
        swap(*this, obj);
        return *this;
    }

    ~anyArrayClass()
    {
        delete[] ptr;
    }
}
```

在上面的示例中，“operator=()”的参数是通过值传递的，该值调用复制构造函数来创建“operator=()”本地的 anyArrayClass 对象。然后用“*this”对象交换 temp 对象的值(赋值运算符调用的 LHS)。

**优势:**

1.  因为参数是通过值传递的，所以不需要更多的自我赋值检查(这意味着不需要更多的内存释放)。此外，由于自我分配非常罕见，因此在自我分配的情况下复制的开销应该不成问题。
2.  现在，由于复制构造函数用于创建临时对象，因此，只有创建了临时对象，交换才会完成。基本上我们在那里手动做的，编译器在这里为我们做。
3.  代码可重用性:正如我们所看到的,“operator=()”的主体中没有太多的代码，而是使用复制构造函数和交换函数来完成这项工作。

本文由**碧华纳特**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。