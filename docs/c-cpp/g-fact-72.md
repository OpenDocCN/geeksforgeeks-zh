# ASCII NUL，ASCII 0 ('0 ')和数字文字 0

> 原文:[https://www.geeksforgeeks.org/g-fact-72/](https://www.geeksforgeeks.org/g-fact-72/)

ASCII NUL 和零分别表示为 0x00 和 0x30。ASCII NUL 字符在 C/C++ 中充当字符串的哨兵字符。当程序员在代码中使用“0”时，它将以十六进制形式表示为 0x30。在下面的程序中，整数的二进制表示将填充什么？

```cpp
char charNUL = '\0';

unsigned int integer = 0;

char charBinary = '0';
```

*charNUL* 的二进制形式会将其所有位设置为逻辑 0。*整数*的二进制形式将它的所有位设置为逻辑 0，这意味着每个字节将被 NUL 字符(\ 0)填充。*字符二进制*的二进制形式将被设置为十六进制 0x30 的二进制等价形式。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。