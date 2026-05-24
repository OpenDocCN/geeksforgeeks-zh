# C |字符串|问题 5

> 原文:[https://www.geeksforgeeks.org/c-string-question-5/](https://www.geeksforgeeks.org/c-string-question-5/)

C 程序的以下片段打印了什么？

```cpp
char c[] = "GATE2011"; 
char *p =c; 
printf("%s", p + p[3] - p[1]) ;
```

**(A)**gate 2011
**(B)**E2011
**(C)**2011
**(D)**011

**答案:****(C)**

**解释:**详见注释。

```cpp

char c[] = "GATE2011"; 

 // p now has the base address string "GATE2011" 
char *p = c;  

// p[3] is 'E' and p[1] is 'A'. 
// p[3] - p[1] = ASCII value of 'E' - ASCII value of 'A' = 4 
// So the expression  p + p[3] - p[1] becomes p + 4 which is 
// base address of string "2011" 
printf("%s", p + p[3] - p[1]);  // prints 2011
```