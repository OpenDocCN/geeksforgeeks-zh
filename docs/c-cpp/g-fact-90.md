# 模板和默认参数

> 原文:[https://www.geeksforgeeks.org/g-fact-90/](https://www.geeksforgeeks.org/g-fact-90/)

**c++ 中模板的默认参数:**
和函数默认参数一样，模板也可以有默认参数。例如，在下面的程序中，第二个参数 U 的默认值为 char。

```cpp
#include<iostream>
using namespace std;

template<class T, class U = char> class A
{
public:
    T x;
    U y;
};

int main()
{
    A<char> a;
    A<int, int> b;
    cout<<sizeof(a)<<endl;
    cout<<sizeof(b)<<endl;
    return 0;
}
```

输出:(char 取 1 字节，int 取 4 字节)
2
8

此外，类似于默认函数参数，如果一个模板参数有默认参数，那么它后面的所有模板参数也必须有默认参数。例如，编译器不允许下列程序:

```cpp
#include<iostream>
using namespace std;

template<class T = char, class U, class V = int> class A  // Error
{ 
   // members of A
};

int main()
{

} 
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。