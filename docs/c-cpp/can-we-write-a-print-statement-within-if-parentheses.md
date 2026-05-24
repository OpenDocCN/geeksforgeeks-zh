# 我们可以在 if 括号内写一个 print 语句吗？

> 原文:[https://www . geesforgeks . org/can-we-write-a-print-statement-in-if-括号/](https://www.geeksforgeeks.org/can-we-write-a-print-statement-within-if-parentheses/)

[If-Else](https://www.geeksforgeeks.org/decision-making-c-c-else-nested-else/) 是一个决策语句，其结果要么是**真**要么是**假**。如果语句接受布尔值–如果值为真，则它将执行其下的语句块，否则不执行。如果没有花括号 **'{'** 和 **'}'** 在 If(条件)之后，那么默认情况下 if 语句将认为紧接在下面的语句在其块内。

> [编程语言中的决策语句](https://www.geeksforgeeks.org/top-10-programming-languages-of-the-world-2019-to-begin-with/)决定程序执行的流向。**如果**是这样的决策语句之一。

如果在 If 块内的**条件**处写入了任何 [printf()](https://www.geeksforgeeks.org/return-values-of-printf-and-scanf-in-c-cpp/) 或 [std::cout](https://www.geeksforgeeks.org/difference-between-cout-and-stdcout-in-c/) 语句，则**输出窗口**将获得与在条件处写入的相同的输出，并且该条件将始终被评估为 **true** 。所以 **if** 语句将作为**真**条件执行。下面是同样的插图:

## c++

```cpp
// C++ program to print a string
// within conditional statement
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Always evaluated as true
    if (cout << "Welcome to ") {
        cout << "GeeksforGeeks";
    }
    else
        cout << "GFG";
    return 0;
}
```

**输出:**

```cpp
Welcome to GeeksforGeeks

```