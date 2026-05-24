# C/C++ 棘手程序

> 原文:[https://www.geeksforgeeks.org/c-cpp-tricky-programs/](https://www.geeksforgeeks.org/c-cpp-tricky-programs/)

在日常生活中，我们可能会遇到各种棘手的程序。也许在技术面试、编码测试中，或者在 C/C++ 教室里。

以下是此类计划的列表

*   用双引号(" ")打印文本。
    这看似简单，但初学者在双引号内打印文本时可能会感到困惑。

## C++

```cpp
// CPP program to print double quotes
#include<iostream>

int main()
{
   std::cout << "\"geeksforgeeks\"";
   return 0;
}
```

**输出:**

```cpp
"geeksforgeeks"
```

*   在不使用算术运算符或比较运算符的情况下检查两个数字是否相等。
    最简单的解决方案是使用按位异或运算符(^).我们知道，对于两个相等的数字，异或运算符返回 0。我们将使用这个技巧来解决这个问题。

## C++

```cpp
// C++ program to check if two numbers are equal
// without using arithmetic operators or
// comparison operators
#include <iostream>
using namespace std;

int main()
{
   int x = 10;
   int y = 10;

   if (!(x ^ y))
      cout << " x is equal to y ";
   else
      cout << " x is not equal to y ";

   return 0;
}

// This code is contributed by shivani
```

## C

```cpp
// C program to check if two numbers are equal
// without using arithmetic operators or
// comparison operators
#include<stdio.h>

int main()
{
   int x = 10;
   int y = 10;
   if ( !(x ^ y) )
      printf(" x is equal to y ");
   else
      printf(" x is not equal to y ");
   return 0;
}
```

**输出:**

```cpp
x is equal to y
```

*   不使用分号将所有自然数打印到。
    我们使用递归调用主函数的思想。

## C++

```cpp
// C++ program to print all natural numbers upto
// N without using semi-colon
#include<iostream>

using namespace std;
int N = 10;

int main()
{
  static int x = 1;
  if (cout << x << " " && x++ < N && main())
  { }
  return 0;
}
```

**输出**:

```cpp
1 2 3 4 5 6 7 8 9 10 
```

*   在不使用任何额外变量的情况下交换两个变量的值。

## C++

```cpp
// C++ program to check if two numbers are equal
#include<iostream>

int main()
{
   int x = 10;
   int y = 70;

   x = x + y;
   y = x - y;
   x = x - y;

   cout << "X : " << x << "\n";
   cout << "Y : " << y << "\n";

   return 0;
}
```

**输出:**

```cpp
X : 70
Y : 10
```

*   不使用任何循环或条件来寻找两个数的最大值和最小值的程序。
    最简单的诀窍是——

## C++

```cpp
// CPP program to find maximum and minimum of
// two numbers without using loop and any
// condition.
#include<bits/stdc++.h>

int main ()
{
   int a = 15, b = 20;
   printf("max = %d\n", ((a + b) + abs(a - b)) / 2);
   printf("min = %d", ((a + b) - abs(a - b)) / 2);
   return 0;
}
```

**输出:**

```cpp
max = 20
min = 15
```

*   在 C.
    中使用一进制补码(~)运算符打印无符号整数的最大值这里有一个技巧，可以使用一进制补码运算符找到无符号整数的最大值:

## C

```cpp
// C program to print maximum value of
// unsigned int.
#include<stdio.h>

int main()
{
   unsigned int max;
   max = 0;
   max = ~max;
   printf("Max value : %u ",  max);
  return 0;
}   
```

*   不用“+”运算符求两个整数之和。
    这是一个非常简单的数学把戏。
    我们知道 a+b =–(-a-b)。所以这对我们来说是个骗局。

## C++

```cpp
// CPP program to print sum of two integers
// withtout +
#include<iostream>

using namespace std;
int main()
{
  int a = 5;
  int b = 5;
  int sum = -( -a-b );
  cout << sum;
  return 0;
}
```

**输出:**

```cpp
10
```

*   验证 if 块内部条件的程序。

## C++

```cpp
// CPP program to verifies the condition inside if block
// It just verifies the condition inside if block,
// i.e., cout << "geeks" which returns a non-zero value,
// !(non-zero value) is false, hence it executes else
// Hence technically it only executes else block
#include<iostream>

using namespace std;
int main()
{
    if (!(cout << "geeks"))
    cout <<" geeks ";
    else
    cout << "forgeeks ";

    return 0;
}
```

**输出:**

```cpp
geeksforgeeks
```

*   不使用“/”运算符将整数除以 4 的程序。
    用 4 除整数最有效的方法之一是使用右移位运算符(“> >”)。

## C++

```cpp
// CPP program to divide a number by 4
// without using '/'
#include<iostream>

using namespace std;
int main()
{
   int n = 4;
   n = n >> 2;
   cout << n;
   return 0;
} 
```

**输出:**

```cpp
1
```

*   检查计算机字符顺序的程序。

## C

```cpp
// C program to find if machine is little
// endian or big endian.
#include <stdio.h>

int main()
{
   unsigned int n = 1;
   char *c = (char*)&n;
   if (*c)   
       printf("LITTLE ENDIAN");
   else
       printf("BIG ENDIAN");
   return 0;
}
```

本文由 [**史密莎·迪内什·森瓦尔**](https://auth.geeksforgeeks.org/profile.php?user=Smitha Dinesh Semwal) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。