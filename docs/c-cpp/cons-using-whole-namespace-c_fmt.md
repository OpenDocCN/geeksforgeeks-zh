# 在 C++ 中使用整个命名空间的缺点

> 原文：[https://www.geeksforgeeks.org/cons-using-whole-namespace-c/](https://www.geeksforgeeks.org/cons-using-whole-namespace-c/)

## 命名空间简介

命名空间是一个声明性区域，它为其中的标识符（类型、函数、变量等的名称）提供了一个范围。名称空间用于将代码组织成逻辑组，并防止可能发生的名称冲突，尤其是当您的代码库包含多个库时。

详情请参考 C++ 中对命名空间的[需求](https://www.geeksforgeeks.org/namespace-in-c/)。

## 问题场景

假设我们需要一个软件项目的两个头文件：

1.  `Header1.h`
    - 命名空间 `one`
2.  `Header2.h`
    - 命名空间 `two`

### C++ 代码

**Header1.h:**

```cpp
namespace one
{
    /*Function to print name of the namespace*/
    void print()
    {
        std :: cout << "This is one" << std :: endl;
    }
}
```

**Header2.h:**

```cpp
namespace two
{
    /*Function to print name of the namespace*/
    void print()
    {
        std :: cout << "This is two" << std :: endl;
    }
}
```

**源代码文件:**

```cpp
/*Including headers*/
#include <iostream>
#include "Header1.h"
#include "Header2.h"

/*Using namespaces*/
using namespace std;
using namespace one;
using namespace two;

/*Driver code*/
int main()
{
    /*Ambiguity*/
    print();
}
```

**输出:**

```
Error: Call of overloaded print() is ambiguous.
```

## 解决方案

为了克服这种情况，我们通过范围解析操作符独立使用命名空间对象。

**源代码文件:**

```cpp
/*Including headers*/
#include <iostream>
#include "Header1.h"
#include "Header2.h"

/*Driver code*/
int main()
{
    /*Using function of first header*/
    one :: print();

    /*Using function of second function*/
    two :: print();
}
```

## 参考资料

- [http://www.cplusplus.com/forum/beginner/25538/](http://www.cplusplus.com/forum/beginner/25538/)
- [https://stackoverflow.com/questions/1452721/why-is-using-namespace-std-considered-bad-practice](https://stackoverflow.com/questions/1452721/why-is-using-namespace-std-considered-bad-practice)

## 延伸阅读

- [C++ 中的命名空间（第 2 部分：扩展命名空间、未命名命名空间）](https://www.geeksforgeeks.org/namespace-in-c-set-2-extending-namespace-un-namespace/)
- [C++ 中的命名空间（第 3 部分：创建头文件、嵌套、别名、访问）](https://www.geeksforgeeks.org/namespace-c-set-3-creating-header-nesting-aliasing-access/)

[GeeksforGeeks 命名空间档案](https://www.geeksforgeeks.org/tag/cpp-namespaces/)

本文由 **[Rohit Thapliyal](https://www.linkedin.com/in/rohit-thapliyal-515b5913a/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。