# C |字符串|问题 9

> 原文:[https://www.geeksforgeeks.org/c-string-question-9/](https://www.geeksforgeeks.org/c-string-question-9/)

考虑以下 C 程序段:

```cpp
char p[20]; 
char *s = "string"; 
int length = strlen(s); 
int i; 
for (i = 0; i < length; i++) 
    p[i] = s[length — i]; 
printf("%s", p);
```

程序的输出是？(GATE CS 2004)
**(A)**gni RTS
**(B)**gni rt
**(C)**string
**(D)**无输出被打印

**答案:****(D)**

**解释:**下面让我们考虑线内的 for 循环
p[I]= 1
对于 i = 0，p[i]将为 s[6 — 0]，s[6]为' \0 '
因此 p[0]变为' \ 0 '。p[1]，p[2]中出现什么并不重要…..因为 P[0]不会因为 i > 0 而改变。如果我们打印第一个字符为“\ 0’

[的字符串，则不会打印任何内容。本问题的测验](https://www.geeksforgeeks.org/quiz-corner-gq/)