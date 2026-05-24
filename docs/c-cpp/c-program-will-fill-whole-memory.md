# 将充满整个内存的 C++ 程序

> 原文:[https://www . geesforgeks . org/c-program-will-fill-all-memory/](https://www.geeksforgeeks.org/c-program-will-fill-whole-memory/)

**注意:我们强烈建议在虚拟机中尝试此代码，因为它可能会在 5 秒内挂起您的计算机**

[C/c++ ](https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/)中的动态内存分配是指程序员手动进行内存分配。动态分配的内存在堆上分配，非静态变量和局部变量在堆栈上分配内存

**新关键字**
新运算符表示对堆内存分配的请求。如果有足够的内存，new 运算符初始化内存，并将新分配和初始化的内存的地址返回给指针变量。

使用新运算符的语法:要分配任何数据类型的内存，语法是

```cpp
pointer-variable = new data-type;

```

**删除关键字**
删除以更好更简单的方式执行分配和释放内存任务的。

使用 delete 运算符的语法:要分配任何数据类型的内存，语法是

```cpp
delete pointer-variable; 

```

下面是将填满整个内存的 C++ 程序

```cpp
#include<bits/stdc++.h>

int main()
{
    while (true)
      int *a = new int;  // allocating 
}

```

**输出&解释**
它在任务管理器打开的时候挂起了我的电脑，显示 1 秒钟占用了 890 Mb 内存，然后它也挂起了。它不断给变量提供记忆。为了探索这段代码的更多内容，添加了 delete a 语句，测试时一切正常(没有挂起)。因此，我认为内存块被给定(由于新的 int)，然后被收回(由于 delete a)到下面新代码中的可用空间。

**缓和代码**

```cpp
#include<bits/stdc++.h>
int main()
{
    while (true)
    {
         int *a = new int;   // allocating
         delete a;           // deallocating
    }
}  
```

**参考文献**
[https://www . geeksforgeeks . org/新的和删除的动态内存操作符](https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory)

本文由**阿卡什·莎兰**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。