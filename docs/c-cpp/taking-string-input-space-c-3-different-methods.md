# 在 C 中用空格进行字符串输入(4 种不同的方法)

> 原文:[https://www . geesforgeks . org/taking-string-input-space-c-3-differential-methods/](https://www.geeksforgeeks.org/taking-string-input-space-c-3-different-methods/)

我们可以使用 **scanf("%s "，str)** 在 C 中进行字符串输入。但是，它只接受字符串，直到找到第一个空格。
有 **4 种方法**C 程序接受用户输入形式的带空格的字符串。
让我们有一个名为**str【】**的字符数组(字符串)。因此，我们将变量声明为 **char str[20]** 。

**方法 1 :** 使用**获取**
T5】语法:char *获取(char *str)

## C

```cpp
#include <stdio.h>
int main()
{
   char str[20];
   gets(str);
   printf("%s", str);
   return 0;
}
```

**注意:get()**已从 c11 中移除。所以它可能会在实现时给你一个警告。
我们在这里看到，它不关心数组的大小。所以[缓冲区溢出](https://en.wikipedia.org/wiki/Buffer_overflow)是有可能的。

**方法二:**为了克服上述限制，我们可以使用 **fgets** 作为:
T5】语法: char *fgets(char *str，int size，FILE *stream)
**示例:** fgets(str，20，stdin)；如这里，根据声明，20 是 MAX_LIMIT。

## C

```cpp
#include <stdio.h>
#define MAX_LIMIT 20
int main()
{
   char str[MAX_LIMIT];
   fgets(str, MAX_LIMIT, stdin);
   printf("%s", str);

   return 0;
}
```

**方法 3 :** 使用 **%[^\n]%*c** 内扫
t5】例: scanf("%[^\n]%*c“，str)；

## C

```cpp
#include <stdio.h>
int main()
{
   char str[20];
   scanf("%[^\n]%*c", str);
   printf("%s", str);

   return 0;
}
```

**说明:**此处， **[]** 为[扫集](https://www.geeksforgeeks.org/scansets-in-c/)字符。 **^\n** 告诉输入，直到没有遇到新行。然后，用这个 **%*c** ，它读取换行符，这里使用的 ***** 表示这个换行符被丢弃。
本文由[阿迪蒂亚·库马尔](https://www.linkedin.com/in/aditya-kumar-837315100/)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。

**方法 4 :** 在 scanf 内部使用%[^\n]s。

**例:** scanf("%[^\n]s”，str)；

## C

```cpp
#include <stdio.h>

int main() {
    char str[100];
      scanf("%[^\n]s",str);
      printf("%s",str);
    return 0;
}
```

**说明:**这里，[]是扫描集字符。^\n 告诉输入，直到没有遇到纽林。在这里，我们使用了^ (XOR -Operator ),直到两个字符都不同时，它才为真。一旦字符等于新行(' \n ')，^ (XOR 运算符)给出 false 来读取字符串。所以我们用“%[^\n]s”代替“%s”。所以要得到一行有空间的输入，我们可以用 scanf("%[^\n]s",str)；

本文由[穆克什·帕特尔供稿。](https://www.linkedin.com/in/MukeshPatelB)如果你喜欢 GeeksforGeeks 并且愿意投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org/)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。