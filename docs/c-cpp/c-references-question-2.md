# C++ |参考文献|问题 6

> 原文:[https://www.geeksforgeeks.org/c-references-question-2/](https://www.geeksforgeeks.org/c-references-question-2/)

关于 C++
**(A)** 中的引用，以下哪一项为 FALSE 引用不能为 NULL
**(B)** 一个引用在声明时必须初始化
**(C)** 一旦创建了一个引用，以后就不能再引用另一个对象；它不能被重置。
**(D)** 引用不能引用常量值

**回答:****(D)**

**解释:**我们可以创建一个引用常量的常量引用。例如，下面的程序编译并运行良好。

```cpp
#include<iostream>
using namespace std;

int main()
{
  const int x = 10;
  const int& ref = x;

  cout << ref;
  return 0;
}
```

[本题小考](https://www.geeksforgeeks.org/c-plus-plus-gq/references-gq/)