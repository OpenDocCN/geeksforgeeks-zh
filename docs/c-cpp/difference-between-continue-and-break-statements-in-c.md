# c++ 中继续和中断语句的区别

> 原文:[https://www . geesforgeks . org/continue-and-break-statements-in-c/](https://www.geeksforgeeks.org/difference-between-continue-and-break-statements-in-c/)

Break 和 continue 是同一类型的语句，专门用于改变程序的正常流程，但它们之间仍有一些区别。

> break 语句:break 语句终止最小的封闭循环(即 while、do-while、for 或 switch 语句)
> 
> continue 语句:continue 语句跳过循环语句的其余部分，并导致循环的下一次迭代发生。

**一个理解 break 和 continue 语句区别的例子**

```cpp
// CPP program to demonstrate difference between
// continue and break
#include <iostream>
using namespace std;
main()
{
    int i;
    cout << "The loop with break produces output as: \n";

    for (i = 1; i <= 5; i++) {

        // Program comes out of loop when
        // i becomes multiple of 3.
        if ((i % 3) == 0)
            break;
        else
            cout << i << " "; 
    }

    cout << "\nThe loop with continue produces output as: \n";
    for (i = 1; i <= 5; i++) {

        // The loop prints all values except
        // those that are multiple of 3. 
        if ((i % 3) == 0)
            continue;
         cout << i << " "; 
    }
}
```

**Output:**

```cpp
The loop with break produces output as: 
1 2 
The loop with continue produces output as: 
1 2 4 5

```

程序描述:

在 first for 循环中，我们使用 break 语句。

2.  现在，当循环第一次迭代时，i=1 的值，if 语句计算为 false，因此执行 else condition/语句。
3.  现在循环再次迭代 i= 2 的值，否则语句将被实现，就好像语句计算结果为 false 一样。
4.  循环再次迭代，现在 I = 3；如果条件评估为真并且循环中断。

在第二个 for 循环中，我们使用 continue 语句。

2.  现在，当循环第一次迭代 i=1 时，if 语句的计算结果为 false，因此实现了 else 条件/语句 2。
3.  现在循环再次迭代 i= 2 的值，否则语句将被实现，就好像语句计算结果为 false 一样。
4.  循环再次迭代，现在 I = 3；如果条件评估为真，则代码将在两者之间停止，并开始新的迭代，直到满足结束条件。