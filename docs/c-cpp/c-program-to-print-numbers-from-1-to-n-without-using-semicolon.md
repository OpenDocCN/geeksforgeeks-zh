# C 程序打印 1 到 N 的数字不用分号？

> 原文:[https://www . geesforgeks . org/c-program-to-print-numbers-从-1 到-n-不使用分号/](https://www.geeksforgeeks.org/c-program-to-print-numbers-from-1-to-n-without-using-semicolon/)

如何在 c 语言中不使用任何分号打印从 1 到 N 的数字？

```cpp
#include<stdio.h>
#define N 100

// Add your code here to print numbers from 1
// to N without using any semicolon
```

在上面的代码片段中添加什么代码，使其不包含分号，并打印从 1 到 N 的数字？

**我们强烈建议您最小化浏览器，先自己尝试一下**

**方法 1(递归)**

```cpp
// A recursive C program to print all numbers from 1
// to N without semicolon
#include<stdio.h>
#define N 10

int main(int num)
{
    if (num <= N && printf("%d ", num) && main(num + 1))
    {
    }     
}
```

输出:

```cpp
1 2 3 4 5 6 7 8 9 10 
```

完整运行见[本](https://ide.geeksforgeeks.org/fXCLRM)。感谢乌卡什·特里维迪提出这个解决方案。

**方法 2(迭代)**

```cpp
// An iterative C program to print all numbers from 1
// to N without semicoolon
#include<stdio.h>
#define N 10

int main(int num, char *argv[])
{
while (num <= N && printf("%d ", num) && num++) 
{
} 
}
```

输出:

```cpp
1 2 3 4 5 6 7 8 9 10 
```

完整运行见[本](https://ide.geeksforgeeks.org/1aB7Xo)。感谢 Rahul Huria 提出这个解决方案。

**这些解决方案是如何工作的？**
main()函数可以接收参数。第一个参数是参数计数，如果没有参数传递给它，它的值是 1。第一个参数总是程序名。

```cpp
#include<stdio.h>

int main(int num, char *argv[])
{
   printf("num = %d\n", num);
   printf("argv[0] = %s ", argv[0]);
}
```

输出:

```cpp
num = 1 
argv[0] = <file_name>
```

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论