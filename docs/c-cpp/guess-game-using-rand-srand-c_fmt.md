# 用C语言制作猜谜游戏

## 使用rand()和srand()函数

> 原文：[https://www.geeksforgeeks.org/guess-game-using-rand-srand-c/](https://www.geeksforgeeks.org/guess-game-using-rand-srand-c/)

使用C语言中的 [`srand()`](https://www.geeksforgeeks.org/rand-and-srand-in-ccpp/) 和 [`rand()`](https://www.geeksforgeeks.org/rand-and-srand-in-ccpp/) 函数，可以制作一个简单但有趣的游戏。这个游戏叫做“猜谜游戏”。

**游戏规则：**

*   有三个洞。一只老鼠藏在那三个洞里的一个里。
*   老鼠每次都变换位置。
*   你必须猜测老鼠藏在三个洞里的那个洞。
*   老鼠所在的洞被命名为“R”，其余两个洞被命名为“N”。
*   你带了一些现金。
*   每次进行猜测时，您都会为玩此游戏下注(`amount_bet`)。
*   如果你的猜测是错误的，你就从你的现金中减去赌注。
*   如果你猜对了，你就赢了两倍的现金。
*   继续玩，继续赢，直到没钱为止。

下面是这个简单有趣的游戏的C语言代码：

**注意：** 由于这款游戏从玩家那里获取 `inhand_cash`、`bet_amount` 和猜测的 `rat` 位置的输入，因此这不会在在线编译器中运行。

```c
// Cpp program for guessing game
// using rand() and srand()
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void GuessGame(int amount_bet, int* inhand_cash)
{
    char Hole[3] = { 'N', 'R', 'N' };
    printf("\nWait !! Rat is shuffling its position...\n");
    srand((time(NULL)));
    int i, x, y, temp;

/*Swapping the Rat's (R's) position  five times using
    the random number for random index*/

for (i = 0; i < 5; i++) {
        x = rand() % 3;
        y = rand() % 3;
        temp = Hole[x];
        Hole[x] = Hole[y];
        Hole[y] = temp;
    }

int PlayerGuess;

printf("\nYou may now guess the hole in which Rat is present: ");

scanf("%d", &PlayerGuess);

if (Hole[PlayerGuess - 1] == 'R') {
        (*inhand_cash) += 2 * amount_bet;
        printf("You win ! The holes are as follows: ");
        printf("\"%c %c %c\" ", Hole[0], Hole[1], Hole[2]);
        printf("\nYour inhand_cash is now = %d \n", *inhand_cash);
    }

else {
        (*inhand_cash) -= amount_bet;
        printf("You Loose ! The holes are as follows: ");
        printf("\"%c %c %c\" ", Hole[0], Hole[1], Hole[2]);
        printf("\nYour inhand_cash is now = %d \n", *inhand_cash);
    }
}

int main()
{
    int amount_bet, inhand_cash;
    /*
    You have to guess the hole in which the 
     Rat is hidden among three holes
    The hole in which Rat is present is 
    named as 'R' and rest two are named as 'N'
    If your guess is wrong, you loose the 
    amount_bet from your inhand_cash
    If you guess it right, you win 
     twice the amount_bet in your inhand_cash
    Keep playing and keep winning 
    until you go out of cash
    */

printf("----Enter the inhand_cash you have right now---- : ");

scanf("%d", &inhand_cash);

while (inhand_cash > 0) {
        printf("\nEnter the amount_bet you want to play for : ");
        scanf("%d", &amount_bet);
        if (inhand_cash == 0 || amount_bet > inhand_cash)
            break;
        GuessGame(amount_bet, &inhand_cash);
    }

if (inhand_cash == 0 || amount_bet > inhand_cash) {
        printf("\n\""
               " 🙁 Sorry you don't have enough cash to play more, ");
        printf("Do come next time\""
               "\n");
        printf("Thank You for playing 🙂 \n");
    }
    return 0;
}
```

**注：** *本输出不取自在线编译器*

输出：

```
----Enter the inhand_cash you have right now---- : 1

Enter the amount_bet you want to play for : 1

Wait !! Rat is shuffling its position...

You may now guess the hole in which Rat is present: 1
You Loose ! The holes are as follows: "N N R"
Your inhand_cash is now = 0

" :-( Sorry you don't have enough cash to play more, Do come next time"
Thank You for playing :-)
```