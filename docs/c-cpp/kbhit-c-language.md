# C 语言 kbhit

> 原文:[https://www.geeksforgeeks.org/kbhit-c-language/](https://www.geeksforgeeks.org/kbhit-c-language/)

kbhit()存在于 conio.h 中，用于确定某个键是否被按下。要在程序中使用 kbhit 函数，您应该包含头文件“conio.h”。如果一个键被按下，那么它返回一个非零值，否则返回零。

```cpp
// C++ program to demonstrate use of kbhit()
#include <iostream.h>
#include <conio.h>

int main()
{
    while (!kbhit())
        printf("Press a key\n");

    return 0;
}
```

输出:

```cpp
"Press a key" will keep printing on the 
console until the user presses a key on the keyboard.

```

**注意:** kbhit()不是标准库函数，应该避免。

**使用 kbhit** 提取按键的程序

```cpp
// C++ program to fetch key pressed using
// kbhit()
#include <iostream>
#include <conio.h>
using namespace std;
int main()
{
    char ch;
    while (1) {

        if ( kbhit() ) {

            // Stores the pressed key in ch
            ch = getch();

            // Terminates the loop
            // when escape is pressed
            if (int(ch) == 27)
                break;

            cout << "\nKey pressed= " << ch;
        }
    }
    return 0;
}
```

输出:

```cpp
Prints all the keys that will be pressed on
 the keyboard until the user presses Escape key

```

本文由 [**尼舒辛格 1**](https://auth.geeksforgeeks.org/profile.php?user=nishu.exe) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。