# 一个创造性的 C++ 程序来缩放一个整数的数字

> 原文:[https://www . geesforgeks . org/creative-c-program-zoom-digits-integer/](https://www.geeksforgeeks.org/creative-c-program-zoom-digits-integer/)

写一个 C(或 C++)程序来缩放(放大)整数的数字。它应该从用户那里获取一个整数，并使用某种模式以放大的形式显示该整数的每个数字。

示例:

```cpp
Input : 123
Output : 

  @
 @@
  @
  @
@@@@@
-------------------------------

@@@@
@  @
  @
 @
@@@@
-------------------------------

@@@@@
    @
@@@@@
    @
@@@@@
-------------------------------

```

这个创意程序从用户那里获取一个整数，并在*缩放*后打印该整数的每个数字。

首先使用[字符串流](https://www.geeksforgeeks.org/converting-strings-numbers-cc/)将给定的数字转换为字符串。之后，每个字符(数字)被访问并放入开关盒结构，开关盒结构缩放每个数字并以图案的形式打印。

下面是 C++ 实现

```cpp
// C++ program to zoon digits of an integer
#include <bits/stdc++.h>
using namespace std;

void zoomDigits(int number)
{
    // Converting number to string
    stringstream ss;
    ss << number;
    string str = ss.str();

    for (int k=0; k<str.length(); k++)
    {
        switch(str[k]-'0')
        {
        case 0:
            for (int i=0; i<5; i++)
            {
                for (int j=0; j<5; j++)
                {
                    if (i==0 || i==4)
                        cout << '@';
                    else if (j==0 || j==4)
                        cout << '@';
                    else
                        cout << " ";

                }
                cout << endl;
            }
            cout << "-------------------------------\n\n";
            continue;

        case 1:
            for (int i=0; i<5; i++)
            {
                for (int j=0; j<5; j++)
                {
                    if (j==2)
                        cout << '@';
                    else if ((i==1 && j==1))
                        cout << '@';
                    else if (i==4)
                        cout << '@';
                    else
                        cout << " ";

                }
                cout << endl;
            }
            cout << "-------------------------------\n\n";
            continue;

        case 2:
            for (int i=0; i<5; i++)
            {
                for (int j=0; j<4; j++)
                {
                    if (i==0 && j==4)
                        cout << " ";
                    else if (i==0 || i==4)
                        cout << '@';
                    else if (i==1 && j==0)
                        cout << '@';
                    else if (i==(4-j))
                        cout << '@';
                    else
                        cout << " ";
                }
                cout << endl;
            }
            cout << "-------------------------------\n\n";
            continue;

        case 3:
            for (int i=0; i<5; i++)
            {
                for (int j=0; j<5; j++)
                {
                    if (i==0 || i==2 || i==4)
                        cout << '@';
                    else if (j==4)
                        cout << '@';
                    else
                        cout << " ";
                }
                cout << endl;
            }
            cout << "-------------------------------\n\n";
            continue;

        case 4:
            for (int i=0; i<5; i++)
            {
                for (int j=0; j<5; j++)
                {
                    if (j==4)
                        cout << '@';
                    else if (i==2)
                        cout << '@';
                    else if (j==0 && (i==0 || i==1))
                        cout << '@';
                    else
                        cout << " ";
                }
                cout << endl;
            }
            cout << "-------------------------------\n\n";
            continue;

        case 5:
            for (int i=0; i<5; i++)
            {
                for (int j=0; j<5; j++)
                {
                    if (i==0 || i==2 || i==4)
                        cout << '@';
                    else if ((j==0 && i==1) ||
                             (j==4 && i==3))
                        cout << '@';
                    else
                        cout << " ";
                }
                cout << endl;
            }
            cout << "-------------------------------\n\n";
            continue;

        case 6:
            for (int i=0; i<5; i++)
            {
                for (int j=0; j<5; j++)
                {
                    if (i==0 || i==2 || i==4)
                        cout << '@';
                    else if ((j==0 && (i==1 || i==3)) ||
                                       (j==4 && i==3))
                        cout << '@';
                    else
                        cout << " ";
                }
                cout << endl;
            }
            cout << "-------------------------------\n\n";
            continue;

        case 7:
            for (int i=0 ; i<5; i++)
            {
                for (int j=0 ; j<5; j++)
                {
                    if (i==0 && (j!=4))
                        cout << '@';
                    else if (i==2 && (j==2 || j==4))
                        cout << '@';
                    else if (j==3)
                        cout << '@';
                    else
                        cout << " ";
                }
                cout << endl;
            }
            cout << "-------------------------------\n\n";
            continue;

        case 8:
            for (int i=0; i<5; i++)
            {
                for (int j=0; j<5; j++)
                {
                    if (i==0 || i==2 || i==4)
                        cout << '@';
                    else if ((j==0 && (i==1 || i==3) ||
                            (j==4 && (i==1 || i==3))))
                        cout << '@';
                    else
                        cout << " ";
                }
                cout << endl;
            }
            cout << "-------------------------------\n\n";
            continue;

        case 9:
            for (int i=0; i<5; i++)
            {
                for (int j=0; j<5; j++)
                {
                    if ( i==0 || i==2 || j==4)
                        cout << '@';
                    else if (i==1 && j==0)
                        cout << '@';
                    else
                        cout << " ";
                }
                cout << endl;
            }
            cout << "-------------------------------\n\n";
            continue;
        }
    }
}

// Driver code
int main()
{
    long long number = 12305;
    zoomDigits(number);
    return 0;
}
```

输出:

```cpp

  @
 @@
  @
  @
@@@@@
-------------------------------

@@@@
@  @
  @
 @
@@@@
-------------------------------

@@@@@
    @
@@@@@
    @
@@@@@
-------------------------------

@@@@@
@   @
@   @
@   @
@@@@@
-------------------------------

@@@@@
@
@@@@@
    @
@@@@@
-------------------------------

```

本文由 **MAZHAR IMAM KHAN** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。