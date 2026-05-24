# c++ 中的变量函数模板

> 原文:[https://www . geesforgeks . org/variadic-function-templates-c/](https://www.geeksforgeeks.org/variadic-function-templates-c/)

变量模板是类或函数[模板](https://www.geeksforgeeks.org/templates-cpp/)，可以接受任何变量(零或更多)数量的参数。在 C++ 中，模板只能有固定数量的参数，这些参数必须在声明时指定。然而，可变模板有助于克服这个问题。道格拉斯·格雷戈尔和 Jaakko jrvi 为 C++ 想出了这个特性。

变量参数非常类似于 C++ 中的[数组](https://www.geeksforgeeks.org/arrays-in-c-cpp/)。我们可以轻松地遍历参数，找到模板的大小(长度)，可以通过索引访问值，也可以对模板进行切片。

所以基本上，变量函数模板是可以接受多个参数的函数。

**语法:**

```cpp
*template(typename arg, typename... args)*
*return_type function_name(arg var1, args... var2)*
```

> **注意:**参数必须放在尖括号内。

下面是 C++ 中的一个例子来展示我们如何使用变量函数模板:

## CPP

```cpp
// C++ program to demonstrate working of
// Variadic function Template
#include <iostream>
using namespace std;

// To handle base case of below recursive
// Variadic function Template
void print()
{
    cout << "I am empty function and "
            "I am called at last.\n";
}

// Variadic function Template that takes
// variable number of arguments and prints
// all of them.
template <typename T, typename... Types>
void print(T var1, Types... var2)
{
    cout << var1 << endl;

    print(var2...);
}

// Driver code
int main()
{
    print(1, 2, 3.14,
          "Pass me any "
          "number of arguments",
          "I will print\n");

    return 0;
}
```

**输出**

```cpp
1
2
3.14
Pass me any number of arguments
I will print

I am empty function and I am called at last.
```

记住[模板被编译器](https://www.geeksforgeeks.org/templates-cpp/)用实际函数替换。

**说明:**变量模板的工作原理如下:

*语句，**打印(1，2，3.14，“传任意个数的参数给我”，“我会打印\ n”)；**评估方式如下:*

首先，编译器将语句解析为

```cpp
cout<< 1 <<endl ;
print(2, 3.14, "Pass me any number of arguments", 
      "I will print\n");
```

现在，编译器找到一个 print()函数，它可以接受这些参数，并以类似的方式再次执行变量 print()函数:

```cpp
cout<< 2 <<endl ;
print(3.14, "Pass me any number of arguments", 
      "I will print\n");
```

同样，它被分解成以下形式:

```cpp
cout<< 3.14 <<endl ;
print("Pass me any number of arguments", 
      "I will print\n");
```

```cpp
cout<< "Pass me any number of arguments" <<endl ;
print("I will print\n");
```

```cpp
cout<< "I will print\n" <<endl ;
print();
```

现在，在这一点上，编译器搜索匹配为空函数的函数重载，即没有参数的函数。这意味着所有有 1 个或更多参数的函数都与变量模板匹配，所有没有参数的函数都与空函数匹配。

本文由 **MAZHAR IMAM KHAN** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。