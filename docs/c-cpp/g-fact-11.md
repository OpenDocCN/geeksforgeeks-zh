# getchar()、fgetc()和 getc()的返回类型是什么？

> 原文:[https://www.geeksforgeeks.org/g-fact-11/](https://www.geeksforgeeks.org/g-fact-11/)

在 C 语言中，getchar()、fgetc()和 getc()的返回类型是 int(不是 char)。所以建议将这些函数的返回值赋给一个整型变量。

```cpp
char ch;  /* May cause problems */  
while ((ch = getchar()) != EOF) 
{
   putchar(ch);
}
```

这里有一个版本，使用整数来比较 getchar()的值。

```cpp
int in;  
while ((in = getchar()) != EOF) 
{
   putchar(in);
}
```

详见[本](http://en.wikipedia.org/wiki/C_file_input/output#The_EOF_pitfall)。