# 在 C++ 中不使用循环、递归或 goto，打印一个字符 n 次

> 原文:[https://www . geesforgeks . org/print-a-character-n-times-不使用循环-递归-or-goto-in-cpp/](https://www.geeksforgeeks.org/print-a-character-n-times-without-using-loop-recursion-or-goto-in-cpp/)

给定字符 c 和数字 n，打印字符 c n 次。我们不允许使用循环、递归和 goto。

**示例:**

```cpp
Input : n = 10, c = 'a'
Output : aaaaaaaaaa

Input  : n = 6, c = '\n'
Output :

Input  : n = 6, character = '@'
output : @@@@@@

```

在 C++ 中，有一种用值初始化字符串的方法。它可以用来打印一个字符，我们想打印多少次就打印多少次。声明字符串时，可以使用 c++ 提供的功能对其进行初始化。需要两个参数。首先是我们想要打印特定字符的次数，另一个是字符本身。

下面是说明这一点的实现。

```cpp
// CPP Program to print a character 
// n times without using loop,
// recursion or goto
#include<bits/stdc++.h>
using namespace std;

// print function
void printNTimes(char c, int n)
{
    // character c will be printed n times
    cout << string(n, c) << endl;
}

// driver code
int main()
{
    // no of times a character
    // need to be printed
    int n = 6;
    char c = 'G';

    // function calling
    printNTimes(c, n);

    return 0; 
}
```

输出:

```cpp
GGGGGG

```

**另一种方法:**我们知道，每次创建一个类的对象时，都会调用该类的构造函数，我们可以利用它来打印构造函数内部的字符，并创建该类的 **N** 个对象。

```cpp
#include<bits/stdc++.h>
using namespace std;

class Geeks{

    public:
        Geeks(){
            cout<<"@ ";
        }

};

int main(){
    int N =6;

    Geeks obj[N];
    return 0;
}
```

输出:

```cpp
@ @ @ @ @ @

```