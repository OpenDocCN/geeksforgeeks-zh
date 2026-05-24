# C++中计算 LCM 的内置函数

> 原文：[https://www.geeksforgeeks.org/inbuilt-function-calculating-lcm-cpp/](https://www.geeksforgeeks.org/inbuilt-function-calculating-lcm-cpp/)

很多时候我们在编程的时候，需要计算两个数之间的最小公倍数(LCM)。在这个帖子中，我们已经讨论了如何[找到 LCM。代替定义然后使用计算 lcm 的函数，我们可以简单地使用一个内置的函数](https://www.geeksforgeeks.org/lcm-of-given-array-elements/)[boost](http://contribute.geeksforgeeks.org/advance-c-with-boost-library/)c++库，`boost::math::lcm()`。

为了使用这个函数，我们必须声明一个头文件`<boost/math/common_factor.hpp>`。

## 语法

```
boost::math::lcm(m, n)
```

参数：`m`, `n`
返回值：如果`m`或`n`中任一为零则返回0，否则返回`mod(m)`和`mod(n)`的最小公倍数。

## 示例

```cpp
// CPP program to illustrate
// boost::math::lcm function of C++ 
#include <iostream>
#include <boost/math/common_factor.hpp>

using namespace std;

int main()
{
    cout << "LCM(10,20) = " << boost::math::lcm(10,20) 
         << endl;
    return 0;
}
```

输出：

```
LCM(10,20) = 20
```

## 重要点

1.  该函数将在取两个数字的模后计算 lcm，因此如果任何一个数字为负，它将被转换为其模，然后计算 LCM。
2.  如果任何一个数字是非整数数据类型，那么此函数将抛出错误。

```cpp
// CPP program to illustrate illegal
// behaviour of boost::math::lcm function of C++ 
#include <iostream>
#include <boost/math/common_factor.hpp>

using namespace std;

int main()
{
    cout << "LCM(1.0,20) = " << boost::math::lcm(1.0,20) 
         << endl;
    return 0;
}
```

这段代码会抛出一个错误，因为函数的一个参数是双精度类型，所以这段代码不会起作用。

3.  在 C++17 中，引入了一个用于计算两个数字 LCM 的新 STL 函数 [`std::lcm()`](https://www.geeksforgeeks.org/stdlcm-in-cpp17/)，可以在任何支持 C++17 特性的编译器上使用。

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。