# get()用起来有风险！

> 原文:[https://www.geeksforgeeks.org/gets-is-risky-to-use/](https://www.geeksforgeeks.org/gets-is-risky-to-use/)

考虑下面的程序。

## C

```cpp
void read()
{
   char str[20];
   gets(str);
   printf("%s", str);
   return;
}
```

代码看起来很简单，它从标准输入中读取字符串并打印输入的字符串，但是它受到[缓冲区溢出](http://en.wikipedia.org/wiki/Buffer_overflow)的影响，因为 get()没有进行任何数组绑定测试。get()继续读取，直到看到换行符。
为了避免缓冲区溢出，应该使用 f gets()而不是 get()，因为 fgets()确保读取的字符不超过 MAX_LIMIT。

## C

```cpp
#define MAX_LIMIT 20
void read()
{
   char str[MAX_LIMIT];
   fgets(str, MAX_LIMIT, stdin);
   printf("%s", str);

   getchar();
   return;
}
```

**注意:** fgets()如果读取了“\n”字符，则存储该字符，因此删除该字符必须由程序员显式完成。因此，如果您打算保留换行符，一般建议您的字符串至少可以存储(MAX_LIMIT + 1)个字符。这样做是为了有足够的空间在字符串末尾添加空终止字符' \0 '。

如果不打算保留换行符，那么可以简单地执行以下操作-

## C

```cpp
int len = strlen(str);

// Remove the '\n' character and replace it with '\0'
str[len - 1] = '\0';
```

请在这里随意阅读更多关于 get()和 fgets() [的内容。](https://www.geeksforgeeks.org/fgets-gets-c-language/)

如果你在上面的文章中发现任何不正确的地方，或者你想分享更多关于上面讨论的主题的信息，请写评论。