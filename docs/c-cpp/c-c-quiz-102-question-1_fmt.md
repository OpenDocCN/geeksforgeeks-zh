# C 小测验–102 | 问题 1

> 原文: [https://www.geeksforgeeks.org/c-c-quiz-102-question-1/](https://www.geeksforgeeks.org/c-c-quiz-102-question-1/)

在 C 数据类型的上下文中，下列哪一项是正确的？
**(A)** `unsigned long int` 是有效的数据类型。
**(B)** `long long double` 是有效的数据类型。
**(C)** `unsigned long double` 是有效的数据类型。
**(D)** A)、B)和 C)都是有效的数据类型。
**(E)** A)、B)、C)均为无效数据类型。

**回答:** **(A)**

## 解释

在 C 语言中，`float` 是单精度浮点类型。`double` 是双精度浮点类型。`long double` 往往比 `double` 类型更精确。所以最大的浮点类型是 `long double`。没有 `long long double` 这种类型。如果有人想使用比 `long double` 更大的范围，我们需要定义自己的数据类型，即用户定义的数据类型。此外，类型说明符 `signed` 和 `unsigned` 不适用于浮点类型（`float`、`double`、`long double`）。基本上，浮点类型总是只带符号的。

但是整数类型，即 `int`、`long int` 和 `long long int` 是有效的组合。根据 C 标准，`long int` 至少为 64 位，即 8 字节。默认情况下，整数类型是带符号的。如果我们需要将这些整数类型设为无符号，可以使用类型说明符 `unsigned`。这就是 A) 是正确答案的原因。

[本题小考](https://www.geeksforgeeks.org/c-quiz-102-gq/)