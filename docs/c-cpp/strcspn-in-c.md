# strcspn()在 C

> 原文:[https://www.geeksforgeeks.org/strcspn-in-c/](https://www.geeksforgeeks.org/strcspn-in-c/)

C 库函数**strcpn()**计算两个字符串中出现的第一个字符之前的字符长度。
**语法:**

```cpp
strcspn(const char *str1, const char *str2)

Parameters:
str1 : The Target string in which search has to be made.
str2 : Argument string containing characters
to match in target string.

Return Value:
This function returns the number of characters before the 1st occurrence
of character present in both the string.

```

```cpp
// C code to demonstrate the working of
// strcspn()
#include <stdio.h>
#include <string.h>

int main()
{

    int size;

    // initializing strings
    char str1[] = "geeksforgeeks";
    char str2[] = "kfc";

    // using strcspn() to calculate initial chars
    // before 1st matching chars.
    // returns 3
    size = strcspn(str1, str2);

    printf("The unmatched characters before first matched character :  %d\n", size);
}
```

输出:

```cpp
The unmatched characters before first matched character :  3

```

**实际应用:**这个功能可以有很多实际应用，无论是**文字游戏还是不规则计算器**。本文演示了一个简单的文字游戏。

**规则:**根据这个游戏，2 个玩家玩，一个玩家最初生成一个字符串，并被要求生成一个字符串，该字符串中有尽可能多的不匹配的字符。1 回合后，产生最多不匹配字符的字符串的玩家获胜。

```cpp
// C code to demonstrate the application of
// strcspn()

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main()
{

    int score1 = 0, score2 = 0, k = 0, sizen = 0, size = 0;

    // initial Round1 strings
    char player1[] = "geeks";
    char play2[] = "";

    while (1) {
        // generating random character
        char randoml = 'a' + (random() % 26);
        play2[k++ ] = randoml;

        size = strcspn(play2, player1);

        if (size == sizen) {
            // if the character is present, break
            score2 = size;
            break;
        }
        else {
            sizen = size;
        }
    }

    // initial Round2 strings
    const char player2[] = "geeks";
    char play1[] = "";
    k = 0, sizen = 0;

    while (1) {
        // generating random character
        char randoml = 'a' + (random() % 26);
        play1[k++ ] = randoml;

        size = strcspn(play1, player2);

        if (size == sizen) {

            // if the character is present, break
            score1 = size;
            break;
        }
        else {
            sizen = size;
        }
    }

    if (score1 > score2)
        printf("Player 1 won!! Score : %d", score1);
    else if (score2 > score1)
        printf("Player 2 won!! Score : %d", score2);
    else
        printf("Match Drawn!! Score : %d", score1);
}
```

输出:

```cpp
Match Drawn!! Score : 2

```