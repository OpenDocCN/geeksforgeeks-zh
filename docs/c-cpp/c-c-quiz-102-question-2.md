# C 小测验–102 |问题 2

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-102-question-2/](https://www.geeksforgeeks.org/c-c-quiz-102-question-2/)

在以下 C 中 printf()的上下文中，选择最佳语句。

```cpp
i) printf("%d",8);
ii) printf("%d",090);
iii) printf("%d",00200);
iv) printf("%d",0007000);
```

**(A)** 只有我)会编译。它将打印 8。
**【B】**一)和二)都会编译。I)将打印 8，而 ii)将打印 90
**(C)** 所有 I)、ii)、iii)和 iv)将成功编译，它们将分别打印 8、90、200 & 7000。
**【D】**只有 I)、iii)和 iv)会编译成功。他们将分别打印 8，128 和 3584。

**回答:****(D)**

**解释:**

按照 C 标准，“*一个八进制常量由前缀 0 组成，后面可选地跟有一系列的* *数字 0 到 7。*”

所以 090 无效，因为 0 前缀用于八进制，而 9 不是有效的八进制数字。

[本题小考](https://www.geeksforgeeks.org/c-quiz-102-gq/)