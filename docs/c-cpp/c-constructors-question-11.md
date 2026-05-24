# C++ |构造函数|第 17 题

> 原文:[https://www.geeksforgeeks.org/c-constructors-question-11/](https://www.geeksforgeeks.org/c-constructors-question-11/)

输出？

```cpp
#include<iostream>
#include<string.h>
using namespace std;

class String
{
    char *str;
public:
     String(const char *s);
     void change(int index, char c) { str[index] = c; }
     char *get() { return str; }
};

String::String(const char *s)
{
    int l = strlen(s);
    str = new char[l+1];
    strcpy(str, s);
}

int main()
{
   String s1("geeksQuiz");
   String s2 = s1;
   s1.change(0, 'G');
   cout << s1.get() << " ";
   cout << s2.get();
}
```

**(A)** 极客 sQuiz
极客 sQuiz
**(B)** 极客 sQuiz
极客 squiz
T8】(C)极客 sQuiz
极客 squiz
T12】(D)极客 sQuiz
极客 squiz
T16
T18】答案:T20】(B)T22
T24】解释:编译器创建的复制构造函数在第“字符串 s2 = s1”行中进行浅复制

所以 s1 和 s2 的字符串指针指向同一个位置。

在带有动态内存分配指针的类中，必须有一个用户定义的复制构造函数。

[本题小考](https://www.geeksforgeeks.org/c-plus-plus-gq/constructors-gq/)