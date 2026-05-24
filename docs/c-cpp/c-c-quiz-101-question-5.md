# C 小测验–101 |问题 5

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-101-question-5/](https://www.geeksforgeeks.org/c-c-quiz-101-question-5/)

考虑以下 C 语言中的变量声明和定义

```cpp
i) int var_9 = 1;
ii) int 9_var = 2;
iii) int _ = 3;
```

选择正确的语句 w.r.t .以上变量。
**(A)**I)和 iii)均有效。
**(B)** 只有我)有效。
**(C)**I)和 ii)均有效。
**(D)** 均有效。

**答案:****(A)**

**解释:**在 C 语言中，变量名可以由字母、数字和下划线组成，即 _。但是变量名必须以字母或下划线开头。不能以数字开头。所以有效的变量是 var_9 和 _ 来自上面的问题。即使是两个背靠背的下划线，即 __ 也是一个有效的变量名。偶数 _9 是一个有效的变量。但是 9var 和 9_ 在 c 中是无效变量。这将在编译时被捕获。这就是为什么正确答案是 A)。

[本题小考](https://www.geeksforgeeks.org/c-quiz-101-gq/)