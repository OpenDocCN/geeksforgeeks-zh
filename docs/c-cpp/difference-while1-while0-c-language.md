# C 语言中 while(1)和 while(0)的区别

> 原文:[https://www . geesforgeks . org/difference-while 1-while 0-c-language/](https://www.geeksforgeeks.org/difference-while1-while0-c-language/)

先决条件:[C/c++ 中的 while 循环](https://www.geeksforgeeks.org/loops-in-c-and-c/)
在大多数计算机编程语言中，while 循环是一种控制流语句，允许基于给定的布尔条件重复执行代码。布尔条件为真或假

**而(1)**

这是一个无限循环，它将一直运行，直到一个 break 语句被显式发出。有趣的是，不是 while(1)，而是任何非零整数都会产生与 while(1)类似的效果。因此，while(1)，while(2)或 while(-255)，都只会给出无限循环。

```cpp
while(1) or while(any non-zero integer)
{ 
    // loop runs infinitely
}

```

while(1)的简单用法可以在客户机-服务器程序中使用。在该程序中，服务器以无限 while 循环运行，以接收客户端发送的数据包。
但实际上，在现实世界中使用 while(1)是不可取的，因为它增加了 CPU 的使用，也阻止了代码，即在程序手动关闭之前，不能从 while(1)中出来。而(1)可以用在条件总是需要为真的地方。

## C

```cpp
// C program to illustrate while(1)
#include <stdio.h>
int main()
{
    int i = 0;
    while (1) {
        printf("%d\n", ++ i);
        if (i == 5)
            break; // Used to come
                   // out of loop
    }
    return 0;
}
```

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    int i = 0;
    while (1) {
        cout << ++ i << "\n";
        if (i == 5)
            // Used to come
            // out of loop
            break;
    }
    return 0;
}
```

**Output**

```cpp
1
2
3
4
5

```

**while(0)**
与 while(1)相反。这意味着条件总是假的，因此 while 中的代码永远不会被执行。

```cpp
while(0)
{ 
    // loop does not run
}

```

## C

```cpp
// C program to illustrate while(0)
#include<stdio.h>
int main()
{
  int i = 0, flag=0;
  while ( 0 )
  {
    // This line will never get executed
    printf( "%d\n", ++ i ); 
    flag++ ;
    if (i == 5)
      break;
  }
  if (flag==0)
     printf ("Didn't execute the loop!");
 return 0;
}
```

## C++

```cpp
#include <iostream>
using namespace std;

int main() {
  int i = 0, flag=0;
  while ( 0 )
  {
    // This line will never get executed
    cout << ++ i << "\n"; 
    flag++ ;
    if (i == 5)
      break;
  }
  if (flag==0)
     cout << "Didn't execute the loop!";
 return 0;
}
```

**Output**

```cpp
Didn't execute the loop!
```

本文由**安西卡·戈亚尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。