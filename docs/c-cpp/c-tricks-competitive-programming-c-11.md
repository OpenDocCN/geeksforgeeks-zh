# 竞争性编程的 C++ 技巧(针对 C++ 11)

> 原文:[https://www . geesforgeks . org/c-ticks-competitive-programming-c-11/](https://www.geeksforgeeks.org/c-tricks-competitive-programming-c-11/)

我们已经在下面的帖子中讨论了一些技巧。在这篇文章中，讨论了更多的技巧。

[在竞争性编程中高效编写 C/C++ 代码](https://www.geeksforgeeks.org/writing-cc-code-efficiently-in-competitive-programming/)

虽然练习是确保在编程竞赛中提高性能的唯一方法，但是掌握一些技巧可以确保优势和快速调试。

**1)在不使用%运算符的情况下检查数字是偶数还是奇数:**
虽然这个技巧并不比使用%运算符好多少，但有时是有效的(对于大数)。使用&运算符:

```cpp
if (num & 1)
   cout << "ODD";
else
   cout << "EVEN";
```

例:
num = 5
二进制:“101 & 1”会是 001，所以真
num = 4
二进制:“100 & 1”会是 000，所以假。

**2)快速乘除 2**
乘除 2 表示向左移动所有位，乘除 2 表示向右移动。

示例:2(二进制 10):向左移动 4(二进制 100)和向右移动 1(二进制 1)

```cpp
n = n << 1;   // Multiply n with 2
n = n >> 1;   // Divide n by 2
```

**3)使用 XOR 交换 2 个数字:**
这种方法速度快，不需要使用第 3 个变量。

```cpp
// A quick way to swap a and b
a ^= b;
b ^= a;
a ^= b;
```

**4)避免使用 strlen():**

```cpp
//  Use of strlen() can be avoided by:
for (i=0; s[i]; i++) 
{ 
}
// loop breaks when the character array ends.
```

**5)在 STL 中使用 retain _ back()(这里讨论了、[这里](https://www.geeksforgeeks.org/inserting-elements-in-stdmap-insert-emplace-and-operator/)和[这里](https://www.geeksforgeeks.org/insertion-deletion-stl-set-c/) )**
代替 push_back()可以使用 retain _ back，因为它要快得多，而不是在其他地方分配内存，然后追加它直接在容器中分配内存。

**6)内置 GCD 函数:** C++ 内置 GCD 函数，无需显式编码。语法:__gcd(x，y)；

**7)使用内联函数:**我们可以创建内联函数并使用它们，而无需在比赛期间对它们进行编码。例子:(a)筛选函数，(b)回文函数。

**8)数组的最大大小:**我们必须知道在主函数中声明的数组的最大大小是 10^6 的数量级，但是如果您声明数组是全局的，那么您可以声明它的大小直到 10^7.

**9)计算最高有效位:**计算任意数字对数的最高有效位都可以直接用来计算。

```cpp
Suppose the number is N then 
Let double K = log10(N);
now K = K - floor(K);
int X = pow(10, K);
X will be the most significant digit.
```

**10)直接计算位数:**要计算一个数字的位数，不用循环，可以高效使用 log:

```cpp
Number of digits in N =floor(log10(N)) + 1;  
```

**11) [知道一个数是否是 2 的幂的有效技巧](https://www.geeksforgeeks.org/program-to-find-whether-a-no-is-power-of-two/)** 用通常的除法技巧，复杂度是 O(logN)，但是可以用 O(v)来求解，其中 v 是二进制形式的数的位数。

```cpp
/* Function to check if x is power of 2*/
bool isPowerOfTwo (int x)
{
  /* First x in the below expression is 
    for the case when x is 0 */
  return x && (!(x&(x-1)));
}
```

**12) C++ 11 内置了以下算法:**

```cpp
       // are all of the elements positive?
       all_of(first, first+n, ispositive()); 

      // is there at least one positive element?
      any_of(first, first+n, ispositive());

      // are none of the elements positive?
      none_of(first, first+n, ispositive()); 
```

详见【C++ STL 中的[数组算法(all_of，any_of，none_of，copy_n 和 itoa)](https://www.geeksforgeeks.org/useful-array-algorithms-in-c-stl/) 。

**13)复制算法:用于将元素从一个容器复制到另一个容器。**

```cpp
int source[5] = {0, 12, 34, 50, 80};
int target[5];
// copy 5 elements from source to target
copy_n(source, 5, target);

```

详见【C++ STL 中的[数组算法(all_of，any_of，none_of，copy_n 和 itoa)](https://www.geeksforgeeks.org/useful-array-algorithms-in-c-stl/) 。

**14)Iota 算法**算法 Iota()创建一系列顺序递增的值，就好像首先给*赋值，然后使用前缀++ 递增该值。在下面的列表中，iota()将连续的值{10，11，12，13，14}分配给数组 arr，并将{'a '，' b '，' c'}分配给字符数组 c[]。

```cpp
int a[5] = {0};
char c[3] = {0};

// changes a to {10, 11, 12, 13, 14}
iota(a, a+5, 10); 
iota(c, c+3, 'a'); // {'a', 'b', 'c'}
```

详见【C++ STL 中的[数组算法(all_of，any_of，none_of，copy_n 和 itoa)](https://www.geeksforgeeks.org/useful-array-algorithms-in-c-stl/) 。

**15)二进制形式的初始化:**在 C++ 11 中，赋值也可以二进制形式进行。

```cpp
// C++ code to demonstrate working of 
// "binary" numbers
#include<iostream>
using namespace std;
int main()
{
    auto number = 0b011;
    cout << number;
    return 0;
}
```

输出:

```cpp
3
```

**16)使用“和”**虽然不是一个非常有效的方法，但是这个技巧帮助你只使用条件运算符，而不是键入&。

```cpp
// C++ code to demonstrate working of "and"
#include<iostream>
using namespace std;
int main()
{
    int a = 10;
    if (a < 20 and a > 5)
      cout << "Yes";
    return 0;
}
```

输出:

```cpp
Yes
```

本文由**雅什·科德西亚**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。