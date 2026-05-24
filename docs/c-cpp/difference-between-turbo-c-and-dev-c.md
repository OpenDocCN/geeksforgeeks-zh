# Turbo c++ 和 Dev C++

的区别

> 原文:[https://www . geeksforgeeks . org/turbo-c 和-dev-c 之间的区别/](https://www.geeksforgeeks.org/difference-between-turbo-c-and-dev-c/)

**1。Turbo C++ (TC) :**
是一款用于 C 和 CPP 语言的编译软件。最初发布于 1990 年 5 月，但第一个稳定版本于 2008 年 9 月发布。与 Dev C++ 相比，加载它需要更多的内存和时间。Turbo C++ 是我们大多数人在学校/大学开始编码生活的编译器。

**2。Dev C++ :**
Dev C++ 也用于 C 和 CPP 语言。第一次稳定发布是在 2015 年 4 月。与 Turbo C++ 相比，它速度很快。Dev C++ 与我们在编码竞赛中使用的在线编译器非常相似。

让我们用一个程序来看看两者的区别。要理解这一点，你必须具备 C++ 的基础知识。

**Turbo c++ 中的代码:**

```cpp
#include <conio.h>
#include <iostream.h>
void main()
{
   clrscr();
   cout << "Hello Geeks!" ; 
   getch(); 
}
```

**注–**
本程序仅按照 Turbo C++ 软件的标准编写。这可能不会在在线编译器或 Dev C++ 中运行。

**Dev c++ 中的代码:**

```cpp
#include <iostream>
using namespace std;
int main()
{
   cout << "Hello Geeks" ; 
   return 0; 
} 
```

**Turbo c++ 和 Dev C++ 的区别:**

<center>

| 没有 | Turbo C++ 程序 | Dev C++ |
| --- | --- | --- |
| 1. | 在 Turbo C++ 中，有 2 个头文件。#include <conio.h>是额外的，在 Dev C++ 的代码中不存在。这个头文件基本上包含了 getch()函数，用来成功返回程序。</conio.h> | 在 Dev C++ 代码中，我们使用默认情况下由 main()函数包含的 return 0。 |
| 2. | 命名空间包含基本的 cin、cout 等关键词。但是我们在 Turbo C++ 中不使用它，因为我们编写的 iostream.h 本身包含了一切。 | 在 Dev C++ 中，我们编写命名空间 std，因为头文件 iostream 不包含 cin、cout。 |
| 3. | 在 Turbo C++ 中，以前的程序数据保存为垃圾，下次出现在屏幕上。所以需要 clrscr()函数。 | 在 Dev C++ 中，每次编译和运行后，都会弹出一个新窗口。所以，我们不需要清除以前程序使用的屏幕。 |
| 4. | 在 Turbo C++ 中，默认情况下安装图形。 | 在 Dev C++ 中，我们需要手动安装显卡。 |

</center>