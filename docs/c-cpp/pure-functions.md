# 纯功能

> 原文:[https://www.geeksforgeeks.org/pure-functions/](https://www.geeksforgeeks.org/pure-functions/)

如果一个函数总是为相同的参数值返回相同的结果，并且它没有像修改参数(或全局变量)或输出某些东西那样的副作用，那么它被称为[纯函数](http://en.wikipedia.org/wiki/Pure_function)。调用纯函数的唯一结果是返回值。纯函数的例子有 strlen()，pow()，sqrt()等。不纯函数的例子有 printf()，rand()，time()，等等。

如果一个函数被称为纯编译器，那么[循环优化](http://en.wikipedia.org/wiki/Loop_optimization)和[子表达式消除](http://en.wikipedia.org/wiki/Common_subexpression_elimination)可以应用于它。在 GCC 中，我们可以使用“pure”属性将函数标记为 pure。

```cpp
__attribute__ ((pure)) return-type fun-name(arguments1, …)
{
    /* function body */
}

```

下面是一个返回传递的整数平方的纯函数示例。

```cpp
__attribute__ _((pure)) int my_square(int val)
{
    return val*val;
}
```

考虑下面的例子

```cpp
for (len = 0; len < strlen(str); ++ len)
    printf("%c", toupper(str[len]));
```

如果“strlen()”函数没有被标记为纯函数，那么编译器将在循环的每次迭代中调用“strlen()”函数，如果函数被标记为纯函数，那么编译器知道“strlen()”函数的值对于每次调用都是相同的，这就是编译器优化 for 循环并生成如下代码的原因。

```cpp
int len = strlen(str);

for (i = 0; i < len; ++ i)
    printf("%c", toupper((str[i]));
```

让我们编写自己的纯函数来计算字符串长度。

```cpp
__attribute__ ((pure)) size_t my_strlen(const char *str)
{
    const char *ptr = str;
    while (*ptr)
       ++ ptr;

    return (ptr – str);
}
```

将函数标记为纯表示假设函数“my_strlen()”的调用次数比程序所说的要少。

本文由“纳伦德拉·康拉尔卡尔”编辑，GeeksforGeeks 团队审核。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。