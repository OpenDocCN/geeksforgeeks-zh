# C++ 浮点操作(fmod()，余数()，cmath 中的 remquo()…)

> 原文:[https://www . geeksforgeeks . org/浮点-操作-数学-h/](https://www.geeksforgeeks.org/floating-point-manipulation-math-h/)

像整数一样，C++ 11 引入了一些基本的内置函数，用于处理日常编程和竞争性编程所必需的浮点数的简单数学计算。本文讨论了介绍的一些功能。

**1。fmod()** :此函数用于返回其参数中提到的 2 个浮点数的**余数(模)。计算的商被**截断**。**

**2。余数()**:这个函数也用来返回其参数中提到的 2 个浮点数的**余数(模)。计算的商是**四舍五入**。**

**3。remquo()** :此函数返回余数，并将余数存储在作为参数传递的变量引用中。**这个函数接受 3 个参数，分子，分母和变量的引用，其中必须存储商。**

```cpp
// C++ code to demonstrate working of
// fmod(), remainder() and remquo()
#include <iostream>
#include <cmath>
using namespace std;

int main() {

   double a, b, c, d, f;
   int g;

   // initializing values
   a = 9.6;
   b = 3.5;

   // using fmod() to compute the remainder
   // computes 2 as quotient (truncated)
   // returns 2.6 as remainder
   d = fmod(a,b);

   // using remainder() to compute the remainder
   // computes 3 as quotient (rounded)
   // returns -0.9 as remainder
   c = remainder(a,b);

   // using remquo() to return quotient and remainder
   // quotient stored in g
   f = remquo(a,b,&g);

   cout << "The remainder computed using fmod() is : " <<d;
   cout << endl;

   cout << "The remainder computed using remainder() is : " <<c;
   cout << endl;

   cout << "The remainder part of " << a <<"/" << b << " is : " << f;
   cout << endl;
   cout << "The quotient part of " << a <<"/" << b << " is : " << g ;
   cout << endl;

}
```

输出:

```cpp
The remainder computed using fmod() is : 2.6
The remainder computed using remainder() is : -0.9
The remainder part of 9.6/3.5 is : -0.9
The quotient part of 9.6/3.5 is : 3

```

**4。copysign()** :该函数返回一个数字，其**数值为第一个参数，符号为第二个参数**。

**5。nextafter()** :该函数计算第一个参数在第二个参数方向上的下一个可表示值**。**

```cpp
// C++ code to demonstrate working of
// nextafter() and copysign()
#include <iostream>
#include <cmath>
using namespace std;

int main() 
{    
   double a, b, c;

   // initializing values
   a = 9.6;
   b = -3.5;
   c = 0.0;

   // using copysign()
   cout << "The value returned after copysigning is : ";
   cout << copysign(a,b);

   cout << endl;

   // using nextafter() to compute next approximated value 
   cout << "The next value approximated is : ";
   cout << nextafter(c,b);
}
```

输出:

```cpp
The value returned after copysigning is : -9.6
The next value approximated is : -4.94066e-324

```

**6。fmin()** :返回两个参数中最小的**。**

****7。fmax()** :返回两个参数中最大的**。****

******8。fdim()** :返回作为参数传递的数字的**正差**。****

******9。fma()** :该函数取 **3 个参数**，计算后返回**乘加****x * y+z**值。****

```cpp
**// C++ code to demonstrate working of
// fmin(), fmax(), fdim(), fma()
#include <iostream>
#include <cmath>
using namespace std;

int main() 
{    
   double a, b, c;

   // initializing values
   a = 2.5;
   b = 2.0;
   c = 2.5;

   // using fmax() to compute maximum of two numbers
   cout << "The largest of 2 numbers is : ";
   cout << fmax(a,b);

   cout << endl;

   // using fmin() to compute smallest of two numbers
   cout << "The smallest of 2 numbers is : ";
   cout << fmin(a,b);

   cout << endl;

   // using fdim() to compute positive difference of two numbers
   cout << "The positive difference of 2 numbers is : ";
   cout << fdim(a,b);

   cout <<  endl;

   // using fma() to compute multiply-add
   cout << "The multiply-add of 3 numbers is : ";
   cout << fma(a,b,c);   
}**
```

****输出:****

```cpp
**The largest of 2 numbers is : 2.5
The smallest of 2 numbers is : 2
The positive difference of 2 numbers is : 0.5
The multiply-add of 3 numbers is : 7.5** 
```

****本文由 **[曼吉特·辛格(S. Nandini)](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。****

****如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。****