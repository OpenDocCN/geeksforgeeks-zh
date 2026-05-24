# C 中的变量和关键词

> 原文:[https://www.geeksforgeeks.org/variables-and-keywords-in-c/](https://www.geeksforgeeks.org/variables-and-keywords-in-c/)

一个**变量**简单来说就是一个存储空间，里面分配了一些内存。基本上，用来存储某种形式数据的变量。不同类型的变量需要不同的内存量，并且有一些特定的操作集可以应用于它们。

**变量声明:**
典型的变量声明形式如下:

```cpp
  type variable_name;
    or for multiple variables:
  type variable1_name, variable2_name, variable3_name;
```

变量名可以由字母(大写和小写)、数字和下划线“_”字符组成。但是，名称不能以数字开头。

**区别 b/w 变量声明和定义**
变量声明是指变量在首次使用前首先声明或引入的部分。变量定义是给变量分配一个内存位置和值的部分。大多数时候，变量声明和定义是一起完成的。

请参阅以下 C 程序以获得更好的说明:

## C

```cpp
#include <stdio.h>
int main()
{
    // declaration and definition of variable 'a123'
    char a123 = 'a';

    // This is also both declaration and definition as 'b' is allocated
    // memory and assigned some garbage value.  
    float b; 

    // multiple declarations and definitions
    int _c, _d45, e;

    // Let us print a variable
    printf("%c \n", a123);

    return 0;
}
```

**输出:**

```cpp
a
```

有可能有单独的声明和定义吗？
在[外部变量](https://www.geeksforgeeks.org/understanding-extern-keyword-in-c/)和[功能](https://www.geeksforgeeks.org/functions-in-c/)的情况下是可能的。详见本第[题 1。](https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-1/)

**定义变量的规则**

1.  变量可以有字母、数字和下划线。
2.  变量名可以以字母开头，只能以下划线开头。不能以数字开头。
3.  变量名中不允许有空格。
4.  变量名不能是任何保留字或关键字，例如 int、goto 等。

**C 中变量的类型**
1。**局部变量**
在函数或块内部声明和使用的变量称为局部变量。
其范围仅限于功能或区块。它不能在街区外使用。局部变量需要
初始化后才能使用。

**示例–**

## C

```cpp
#include <stdio.h>
void function() {
  int x = 10; // local variable
}

int main()
{
  function();
}
```

在上面的代码中 x 只能在函数()的范围内使用。在主函数中使用它会产生错误。

2.**全局变量**
在函数或块外声明的变量称为全局变量。
程序开始时声明。它适用于所有功能。

**示例–**

## C

```cpp
#include <stdio.h>
int x = 20;//global variable
void function1()
{
  printf("%d\n" , x);
}
void function2()
{
  printf("%d\n" , x);
}
int main() {

  function1();
  function2();
    return 0;
}
```

**Output** 

```cpp
20
20
```

在上面的代码中，两个函数都可以使用全局变量 x，因为我们已经知道所有函数都可以访问全局变量。

3.**静态变量**
在多个函数调用之间保持其值的变量称为静态变量。
用 static 关键字声明。

**示例-**

## C

```cpp
#include <stdio.h>
void function(){ 
int x = 20;//local variable 
static int y = 30;//static variable 
x = x + 10; 
y = y + 10; 
printf("\n%d,%d",x,y); 
} 
int main() {

  function();
  function();
  function();
  return 0;
}
```

**Output**

```cpp
30,40
30,50
30,60
```

在上面的例子中，每当函数被调用时，局部变量将总是打印相同的值，而静态变量将在每次函数调用中打印递增的值。

4.**自动变量**
C 中所有在块内声明的变量，默认都是自动变量。我们
可以使用 auto 关键字显式声明一个自动变量。自动变量类似于
局部变量。

**示例–**

## C

```cpp
#include <stdio.h>
void function()
{
  int x=10;//local variable (also automatic) 
  auto int y=20;//automatic variable
}
int main() {

    function();
    return 0;
}
```

在上面的例子中，x 和 y 都是自动变量。唯一不同的是变量 y 是用 **auto** 关键字显式声明的。

5.**外部变量**
外部变量可以在多个 C 文件之间共享。我们可以使用 **extern** 关键字声明外部变量。

**示例:**

```cpp
  myfile.h

  extern int x=10;//external variable (also global)  

  program1.c
  #include "myfile.h"  
  #include <stdio.h>  
  void printValue(){  
  printf("Global variable: %d", global_variable);  
  }
```

在上例中，x 是一个外部变量，用于多个文件。

**关键词**是 C 中特定的保留词，每个保留词都有与之相关的特定特征。几乎所有帮助我们使用 C 语言功能的单词都包含在关键词列表中。所以你可以想象关键词列表不会很小！

C 中总共有 44 个关键词(C89–32，C99–5，C11–7):

```cpp
auto        extern        short        while
break        float        signed        _Alignas
case        for        sizeof        _Alignof
char        goto        static        _Atomic
const        if        struct        _Bool
continue    inline        switch        _Complex
default     int        typedef        _Generic
do         long        union        _Imaginary
double         register    unsigned    _Noreturn
else         restrict    void        _Static_assert
enum         return        volatile    _Thread_local
```

这些关键词中的大多数已经在 [C 语言](https://www.geeksforgeeks.org/c/)的各个小节中讨论过了，比如数据类型、存储类、控制语句、函数等。

让我们讨论一些允许我们使用 C 语言基本功能的其他关键词:

[**const**](https://www.geeksforgeeks.org/const-qualifier-in-c/) : const 可以用来声明常量变量。常量变量是初始化时不能改变其值的变量。或者换句话说，分配给它们的值不能在程序中进一步修改。
**语法:**

```cpp
const data_type var_name = var_value;
```

注意:常量变量必须在声明过程中初始化。const 关键字也用于指针。请参考 C 中的[常量限定词进行理解。](https://www.geeksforgeeks.org/const-qualifier-in-c/)

[**extern**](https://www.geeksforgeeks.org/understanding-extern-keyword-in-c/) : extern 只是告诉我们变量是在别处定义的，而不是在使用它的同一个块内。基本上，该值在不同的块中被分配给它，并且这也可以在不同的块中被覆盖/改变。所以外部变量只不过是一个用合法值初始化的全局变量，在这里它被声明以便在其他地方使用。它可以在任何功能/块中访问。此外，通过在任何函数/块中的声明/定义之前放置“extern”关键字，也可以将普通全局变量设置为 extern。这基本上意味着我们没有初始化一个新的变量，而是只使用/访问全局变量。使用外部变量的主要目的是，它们可以在作为大型程序一部分的两个不同文件之间访问。
**语法:**

```cpp
extern data_type var_name = var_value;
```

**static** : static 关键字用于声明静态变量，在用 C 语言编写程序时常用。静态变量有一个属性，即使超出了它们的范围，也能保持它们的值！因此，静态变量在其作用域中保留了最后一次使用的值。所以我们可以说它们只初始化一次，一直存在到程序终止。因此，没有分配新的内存，因为它们没有被重新声明。它们的范围局限于它们被定义的功能。全局静态变量可以在该文件中的任何地方访问，因为它们的范围是文件的本地范围。默认情况下，编译器会为它们赋值 0。
语法:

```cpp
static data_type var_name = var_value;
```

**void** : void 是一种特殊的数据类型。但是是什么让它如此特别呢？void，顾名思义，是一种空数据类型。意思是它什么都没有或者没有价值。例如，当它用作函数的返回数据类型时，它只是表示函数不返回值。类似地，当它被添加到函数标题时，它表示该函数没有参数。
注意:void 在指针上也有重要的用途。请参考中的[空指针进行理解。](https://www.geeksforgeeks.org/void-pointer-c-cpp/)

**typedef** : typedef 用于给已经存在的或者甚至是自定义的数据类型赋予一个新的名称(比如一个结构)。它有时非常方便，例如，当您定义的结构的名称很长或者您只需要一个现有数据类型的简写符号时。

让我们实现上面讨论过的关键词。看看下面的代码，它是一个演示这些关键字的工作示例:

## C

```cpp
#include <stdio.h>

// declaring and initializing an extern variable
extern int x = 9;

// declaring and initializing a global variable
// simply int z; would have initialized z with
// the default value of a global variable which is 0
int z=10;

// using typedef to give a short name to long long int
// very convenient to use now due to the short name
typedef long long int LL;

// function which prints square of a no. and which has void as its
// return data type
void calSquare(int arg)
{
    printf("The square of %d is %d\n",arg,arg*arg);
}

// Here void means function main takes no parameters
int main(void)
{
    // declaring a constant variable, its value cannot be modified
    const int a = 32;

    // declaring a  char variable
    char b = 'G';

    // telling the compiler that the variable z is an extern variable
    // and has been defined elsewhere (above the main function)
    extern int z;

    LL c = 1000000;

    printf("Hello World!\n");

    // printing the above variables
    printf("This is the value of the constant variable 'a': %d\n",a);
    printf("'b' is a char variable. Its value is %c\n",b);
    printf("'c' is a long long int variable. Its value is %lld\n",c);
    printf("These are the values of the extern variables 'x' and 'z'"
    " respectively: %d and %d\n",x,z);

    // value of extern variable x modified
    x=2;

    // value of extern variable z modified
    z=5;

    // printing the modified values of extern variables 'x' and 'z'
    printf("These are the modified values of the extern variables"
    " 'x' and 'z' respectively: %d and %d\n",x,z);

    // using a static variable
    printf("The value of static variable 'y' is NOT initialized to 5 after the "
            "first iteration! See for yourself :)\n");

    while (x > 0)
    {
        static int y = 5;
        y++ ;
        // printing value at each iteration
        printf("The value of y is %d\n",y);
        x--;
    }

    // print square of 5
    calSquare(5);

    printf("Bye! See you soon. :)\n");

    return 0;
}
```

**输出:**

```cpp
Hello World
This is the value of the constant variable 'a': 32
'b' is a char variable. Its value is G
'c' is a long long int variable. Its value is 1000000
These are the values of the extern variables 'x' and 'z' respectively: 9 and 10
These are the modified values of the extern variables 'x' and 'z' respectively: 2 and 5
The value of static variable 'y' is NOT initialized to 5 after the first iteration! See for yourself :)
The value of y is 6
The value of y is 7
The square of 5 is 25
Bye! See you soon. :)
```

本文由 **Ayush Jaggi** 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。