# C/c++

中的函数

> 原文:[https://www.geeksforgeeks.org/functions-in-c/](https://www.geeksforgeeks.org/functions-in-c/)

函数是一组接受输入、进行特定计算并产生输出的语句。

其思想是将一些通常或重复完成的任务放在一起，并创建一个函数，这样我们就可以调用该函数，而不是针对不同的输入反复编写相同的代码。

函数的一般形式是:

```cpp
return_type function_name([ arg1_type arg1_name, ... ]) { code }  
```

**示例:**
下面是一个简单的 C/C++ 程序演示函数。

## C

```cpp
#include <stdio.h>

// An example function that takes two parameters 'x' and 'y'
// as input and returns max of two input numbers
int max(int x, int y)
{
    if (x > y)
      return x;
    else
      return y;
}

// main function that doesn't receive any parameter and
// returns integer.
int main(void)
{
    int a = 10, b = 20;

    // Calling above function to find max of 'a' and 'b'
    int m = max(a, b);

    printf("m is %d", m);
    return 0;
}
```