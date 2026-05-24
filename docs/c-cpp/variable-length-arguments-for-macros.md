# 宏的可变长度参数

> 原文:[https://www . geesforgeks . org/变长参数用于宏/](https://www.geeksforgeeks.org/variable-length-arguments-for-macros/)

像函数一样，我们也可以将可变长度的参数传递给宏。为此，我们将使用以下预处理器标识符。

为了支持宏中的可变长度参数，我们必须在宏定义中包含省略号(…)。还有“__VA_ARGS__”预处理标识符，它处理提供给宏的可变长度参数替换。串联运算符##(又名粘贴运算符)用于连接变量参数。

让我们举个例子来看看。下面的宏采用可变长度参数，如“printf()”函数。此宏用于错误记录。宏打印文件名后跟着行号，最后打印信息/错误信息。第一个参数“prio”决定了消息的优先级，即它是信息消息还是错误，“stream”可能是“标准输出”或“标准错误”。它在 stdout 上显示 INFO 消息，在 stderr 流上显示 ERROR 消息。

```cpp
#include <stdio.h>

#define INFO    1
#define ERR 2
#define STD_OUT stdout
#define STD_ERR stderr

#define LOG_MESSAGE(prio, stream, msg, ...) do {\
                        char *str;\
                        if (prio == INFO)\
                            str = "INFO";\
                        else if (prio == ERR)\
                            str = "ERR";\
                        fprintf(stream, "[%s] : %s : %d : "msg" \n", \
                                str, __FILE__, __LINE__, ##__VA_ARGS__);\
                    } while (0)

int main(void)
{
    char *s = "Hello";

        /* display normal message */
    LOG_MESSAGE(ERR, STD_ERR, "Failed to open file");

    /* provide string as argument */
    LOG_MESSAGE(INFO, STD_OUT, "%s Geeks for Geeks", s);

    /* provide integer as arguments */
    LOG_MESSAGE(INFO, STD_OUT, "%d + %d = %d", 10, 20, (10 + 20));

    return 0;
}
```

编译并运行上面的程序，它产生下面的结果。

```cpp
  [narendra@/media/partition/GFG]$ ./variable_length 
  [ERR] : variable_length.c : 26 : Failed to open file 
  [INFO] : variable_length.c : 27 : Hello Geeks for Geeks 
  [INFO] : variable_length.c : 28 : 10 + 20 = 30 
  [narendra@/media/partition/GFG]$

```

本文由**纳伦德拉·康拉尔卡尔**整理。如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论