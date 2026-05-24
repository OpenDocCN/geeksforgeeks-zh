# 打印*代替 C

中读取密码的字符

> 原文:[https://www . geesforgeks . org/print-in-place-of-characters-for-reading-password-in-c/](https://www.geeksforgeeks.org/print-in-place-of-characters-for-reading-passwords-in-c/)

在编写 C 程序时，如果你想输入密码，而它在屏幕上不应该是可见的，或者要打印一个*符号。

**例:**

```cpp
Input : abcdefg
Output : *******

```

注意:下面的解决方案使用 getch()，这可能不适用于所有编译器，因为这是非标准函数。

```cpp
// C program to print * 
// in place of characters
#include<stdio.h>
#include<conio.h>
int main(void){
    char password[55];

    printf("password:\n");
    int p=0;
    do{
        password[p]=getch();
        if(password[p]!='\r'){
            printf("*");
        }
        p++ ;
    }while(password[p-1]!='\r');
    password[p-1]='\0';
    printf("\nYou have entered %s as password.",password);
    getch();
}
```

**说明:**基本上是取我们通过 getch()函数输入的字符，打印*代替我们输入的每个字母。

备注:不在这个 IDE 中运行，下载[这个文件](https://media.geeksforgeeks.org/wp-content/uploads/conio.h)在你的终端中运行。

本文由 **Pavan Gopal Rayapati** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。