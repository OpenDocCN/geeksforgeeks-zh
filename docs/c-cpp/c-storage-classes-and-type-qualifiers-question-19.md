# C |存储类和类型限定符|问题 19

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-19/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-19/)

```cpp
#include <stdio.h>
char *fun()
{
    static char arr[1024];
    return arr;
}

int main()
{
    char *str = "geeksforgeeks";
    strcpy(fun(), str);
    str = fun();
    strcpy(str, "geeksquiz");
    printf("%s", fun());
    return 0;
}
```

**(A)**geesforgeks
**(B)**geesquiz
**(C)**geesforgeks geesquiz
**(D)**编译器错误

**答案:****(B)**

**解释:**注意 arr【】是静态的好玩的()所以没有返回地址的问题，arr【】会留下来

```cpp
    strcpy(fun(), str);  // Copies "geeksforgeeks" to arr[]
    str = fun();    // Assigns address of arr to str
    strcpy(str, "geeksquiz");  // copies geeksquiz to str which is address of arr[]
    printf("%s", fun());   // prints "geeksquiz"

```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)