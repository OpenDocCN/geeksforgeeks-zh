# 是 graph() C 库函数

> 原文:[https://www.geeksforgeeks.org/isgraph-c-library-function/](https://www.geeksforgeeks.org/isgraph-c-library-function/)

C 库函数**是 graph()** 检查字符是否是图形字符。
具有图形表示的字符被称为**图形字符**。例如:“:”；”'?'@ '等。

**语法–**

```cpp
#include <ctype.h>
int isgraph(int ch);

```

**返回值–**函数返回**非零值**如果 ch 是除空格以外的任何可打印字符，则返回 0。

对于 ASCII 环境，可打印字符在 **0X21** 到 **0X7E** 的范围内。

**代码–**

```cpp
// code to check graphical character
#include <stdio.h>
#include <ctype.h>

int main()
{
    char var1 = 'g';
    char var2 = ' ';
    char var3 = '1';

    if (isgraph(var1)) 
        printf("var1 = |%c| can be printed\n", var1);
    else 
        printf("var1 = |%c| can't be printed\n", var1);

    if (isgraph(var2)) 
        printf("var2 = |%c| can be printed\n", var2);
    else 
        printf("var2 = |%c| can't be printed\n", var2);

    if (isgraph(var3)) 
        printf("var3 = |%c| can be printed\n", var3);
    else 
        printf("var3 = |%c| can't be printed\n", var3);

    return (0);
}
```

**输出–**

```cpp
var1 = |g| can be printed
var2 = | | can't be printed
var3 = |1| can be printed

```

**代码–**

```cpp
// code to print all Graphical Characters
#include <stdio.h>
#include <ctype.h>

int main()
{ 
    int i;
    printf("In C programming All graphic "
            "characters are: \n");

    for (i = 0; i <= 127; ++ i) 
        if (isgraph(i) != 0)
            printf("%c ", i);    

    return 0;
}
```

**输出–**

```cpp
In C programming All graphic characters are: 
! " # $ % & ' ( ) * +, - . / 0 1 2 3 4 5 6 7 8 9 
: ;  ? @ A B C D E F G H I J K L M N O P Q R S T U
 V W X Y Z [ \ ] ^ _ ` a b c d e f g h i j k l m n
 o p q r s t u v w x y z { | } ~ 

```

本文由**Shivani ghishial**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。