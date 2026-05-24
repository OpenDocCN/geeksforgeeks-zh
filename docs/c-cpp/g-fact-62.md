# 名称空间可以嵌套在 C++ 中吗？

> 原文:[https://www.geeksforgeeks.org/g-fact-62/](https://www.geeksforgeeks.org/g-fact-62/)

在 C++ 中，[命名空间](https://www.geeksforgeeks.org/namespace-in-c/)可以嵌套，命名空间变量的解析是分层的。例如，在下面的代码中，命名空间*内部的*是在命名空间*外部的*内部创建的，它在全局命名空间内部。在*行中“int z = x”*， *x* 指*外::x* 。如果 x 不在*外部*中，那么这个 *x* 会引用全局命名空间中的 *x* 。

```cpp
#include <iostream>

int x = 20;
namespace outer {
  int x = 10;         
  namespace inner {
    int z = x; // this x refers to outer::x
  }
}

int main()
{
  std::cout<<outer::inner::z; //prints 10
  getchar();
  return 0;
}
```

上述程序的输出为 10。

在边节点上，与 C++ 名称空间不同，Java 包不是分层的。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。