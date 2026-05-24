# std::gcd | C++ 查找 gcd 的内置函数

> 原文:[https://www . geesforgeks . org/stdgcd-c-内置-函数-查找-gcd/](https://www.geeksforgeeks.org/stdgcd-c-inbuilt-function-finding-gcd/)

在许多竞争性编程问题中，我们需要找到最大公约数，也称为 **gcd** 。欧几里德算法寻找 gcd 已经讨论过[这里](https://www.geeksforgeeks.org/basic-and-extended-euclidean-algorithms/)。
C++ 内置了计算 GCD 的功能。这个函数存在于头文件中。
**c++ 14 的语法:**

```cpp
 Library: 'algorithm'
 __gcd(m, n) 
Parameter :  m, n
Return Value :  0 if both m and n are zero, 
else gcd of m and n.
```

**c++ 17 的语法:**

```cpp
Library: 'numeric'
gcd(m, n)
Parameter :  m, n
Return Value :  0 if both m and n are zero,
else gcd of m and n.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// gcd function of C++ STL
#include <iostream>
#include <algorithm>
// #include<numeric> for C++ 17

using namespace std;

int main()
{
    cout << "gcd(6, 20) = " << __gcd(6, 20) << endl; // gcd(2.0,8) for C++ 17
}
```

**Output**

```cpp
gcd(6, 20) = 2

```

**注意:**如果 M 或 N 不是整数类型，或者其中任何一个是(可能是 cv 限定的)bool，则程序格式不正确。此外，如果|m|或|n|不能表示为 std::common_type_t 类型的值，则该行为未定义。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// undefined behavior of
// gcd function of C++ STL
#include <iostream>
#include <algorithm>
// #include<numeric> for C++ 17

using namespace std;

int main()
{
    cout << "gcd(6, 20) = " << __gcd(2.0, 8) << endl; // gcd(2.0,8) for C++ 17
}
```

输出:
错误，因为 std::gcd 不支持数据类型 float。
本文由 [**普拉蒂克·查哈尔**](http://www.github.com/pratik-chhajer) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。