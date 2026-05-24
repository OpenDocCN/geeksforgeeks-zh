# c++ 程序输出|第 25 集(宏)

> 原文:[https://www . geesforgeks . org/c 程序输出-set-25-宏/](https://www.geeksforgeeks.org/output-of-c-programs-set-25-macros/)

先决条件–[宏](https://www.geeksforgeeks.org/interesting-facts-preprocessors-c/)

*   **以下程序的输出是什么？**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

#define a 10

int main()
{
    int a = 5;
    cout << "macro variable value: "<< a;
    return 1;
}
```

**输出:**
错误

*   **描述:**编译器无法解析范围，因此不知道打印哪个值，因此出现错误。

*   **以下程序的输出是什么？**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

#define area length * width

int main()
{
    int length = 10, width = 20;
    cout << "macro expression area: " << area;
    return 1;
}
```

**输出:**

```cpp
macro expression area: 200
```

*   **说明:**与第一个问题不同，这里程序中的值需要在宏中替换。一旦控件到达“区域”，它就被宏代码替换，

```cpp
 cout<< "macro expression area: " << length * width;
```

然后长度和宽度的值被替换并计算。

*   **以下程序的输出是什么？**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;

#define sqrt(x) (x*x)

int main()
{
    int a = 3, b;
    b = sqrt(a + 5);
    cout<< "Output of b = " << b;
}
```

**输出:**

```cpp
Output of b =  23
```

*   **描述:**是不是 sqrt(8)BUT sqrt(a+5)；将替换为(a+5 * a+5)；结果为 23，为了使其完美，宏命令应替换为

```cpp
 #define sqrt(x) ( (x) * (x) )
```

*   **以下程序的输出是什么？**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

#define printf(s) cout << s;

int main()
{
    printf("GeeksforGeeks");
    cout << "\nBye Bye";
}
```

**输出:**

```cpp
GeeksforGeeks
Bye Bye
```

*   **说明:**c++ 编译器支持 printf，所以不会抛出任何错误。**宏甚至适用于关键词**和任何类型的语句，如 printf。当控件进入 printf 时，它会像函数调用一样抛出参数，因为它已经被定义了。

*   **以下程序的输出是什么？**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

#define SQRT(x) ( x * x)

int main()
{
    int a,  b= 3;
    a = SQRT(b++);
    cout << a << endl << b;
    return 0;
}
```

**输出:**

```cpp
12
5
```

*   **描述:**a = SQRT(b++)；变成 a = b++ * b++；a = 3 * 4；这里我们使用的是后递增运算符，因此每次执行语句时以及语句执行后，3 都会递增。

[宏的小测验](https://www.geeksforgeeks.org/c-language-2-gq/macro-preprocessor-gq/)
本文由 [I.HARISH KUMAR](https://www.facebook.com/harishkumar.injamuri) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。