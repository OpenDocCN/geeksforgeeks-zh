# 数组成员是否被深度复制？

> 原文:[https://www . geesforgeks . org/are-array-members-deep-copy/](https://www.geeksforgeeks.org/are-array-members-deeply-copied/)

在 C/C++ 中，我们可以将一个结构(或仅 C++ 中的类)变量赋给另一个相同类型的变量。当我们将一个结构变量赋给另一个结构变量时，该变量的所有成员都被复制到另一个结构变量。但是当结构包含指向动态分配内存的指针时会发生什么，如果它包含一个数组呢？

在下面的 C++ 程序中，结构变量 st1 包含指向动态分配内存的指针。当我们将 st1 分配给 st2 时，st2 的 str 指针也开始指向相同的存储位置。这种复制称为[浅复制](http://en.wikipedia.org/wiki/Object_copy#Shallow_copy)。

```cpp
# include <iostream>
# include <string.h>

using namespace std;

struct test
{
  char *str;
};

int main()
{
  struct test st1, st2;

  st1.str = new char[20];
  strcpy(st1.str, "GeeksforGeeks");

  st2 = st1;

  st1.str[0] = 'X';
  st1.str[1] = 'Y';

  /* Since copy was shallow, both strings are same */
  cout << "st1's str = " << st1.str << endl;
  cout << "st2's str = " << st2.str << endl;

  return 0;
}
```

输出:
st1 的 str = XYeksforGeeks
st2 的 str = XYeksforGeeks

那么，数组呢？*需要注意的是，数组成员不是浅拷贝的，编译器会自动对数组成员执行[深拷贝](http://en.wikipedia.org/wiki/Object_copy#Deep_copy)。*。在下面的程序中，结构测试包含数组成员 str[]。当我们将 st1 分配给 st2 时，st2 有一个新的阵列副本。所以当我们改变 st1 的 str[]时，st2 不会改变。

```cpp
# include <iostream>
# include <string.h>

using namespace std;

struct test
{
  char str[20];
};

int main()
{
  struct test st1, st2;

  strcpy(st1.str, "GeeksforGeeks");

  st2 = st1;

  st1.str[0] = 'X';
  st1.str[1] = 'Y';

  /* Since copy was Deep, both arrays are different */
  cout << "st1's str = " << st1.str << endl;
  cout << "st2's str = " << st2.str << endl;

  return 0;
}
```

输出:
st1 的 str = XYeksforGeeks
st2 的 str = GeeksforGeeks

因此，对于 C++ 类，我们不需要为数组成员编写自己的复制构造函数和赋值运算符，因为默认行为是对数组进行深度复制。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。