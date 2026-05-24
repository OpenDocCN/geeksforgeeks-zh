# C 小测验–108 |问题 4

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-108-question-4/](https://www.geeksforgeeks.org/c-c-quiz-108-question-4/)

以下两个函数指针声明是等价的。第二个(即带有 typedef)看起来更干净。

```cpp
/* First Declaration */
int (*funPtr1)(int), (*funPtr2)(int);

/* Second Declaration*/
typedef int (*funPtr)(int);
funPtr funPtr1, funPtr2;
```

**(A)** 真
**(B)** 假

**答案:** **(A)**

**解释:**通常函数指针的数据类型往往是模糊的，这就是为什么它与 *typedef* 结合使用的原因。想象一个函数指针指向一个接受函数指针并返回函数指针的函数。这可以使用 typedef 简化使用，否则会很难阅读/理解！

[本题小考](https://www.geeksforgeeks.org/c-quiz-108-gq/)