# C++ |参考文献|问题 6

> 原文:[https://www.geeksforgeeks.org/c-references-question-6/](https://www.geeksforgeeks.org/c-references-question-6/)

以下 C++ 程序的输出？

```cpp
#include<iostream>
using namespace std;

int main()
{
  int x = 10;
  int& ref = x;
  ref = 20;
  cout << "x = " << x << endl ;
  x = 30;
  cout << "ref = " << ref << endl;
  return 0;
}
```

**(甲)**

```cpp
x = 20
ref = 30
```

**(B)**

```cpp
x = 20
ref = 20
```

**(C)**

```cpp
x = 10
ref = 30
```

**(D)**

```cpp
x = 30
ref = 30
```

**回答:** **(A)**

**解释:** ref 是 x 的别名，所以如果我们改变其中任何一个，我们也可以看到其他的变化。

[本题小考](https://www.geeksforgeeks.org/c-plus-plus-gq/references-gq/)