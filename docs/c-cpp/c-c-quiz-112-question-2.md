# C 小测验–112 |问题 2

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-112-question-2/](https://www.geeksforgeeks.org/c-c-quiz-112-question-2/)

为下面的程序片段选择最佳语句:

```cpp
struct {int a[2];} arr[] = {1,2};
```

**(A)** 没有编译错误，它将创建 2 个元素的数组 arr。arr 的每个元素包含一个由 2 个元素组成的 int 数组的结构字段。arr[0]。[0]是 1，arr 是[1]。[0]将是 2。
**(B)** 没有编译错误，它将创建 2 个元素数组 arr。arr 的每个元素包含一个由 2 个元素组成的 int 数组的结构字段。arr[0]。[0]将是 1 和 arr[0]。a[1]将是 2。第二个元素 arr[1]将是 ZERO，即 arr[1]。a[0]和 arr[1]。[1]将是 0。
**(C)** 没有编译错误，它将创建 1 个元素数组 arr。arr 的每个元素包含一个由 2 个元素组成的 int 数组的结构字段。arr[0]。[0]将是 1 和 arr[0]。a[1]将是 2。

**回答:****(C)**

**说明:**由于数组 arr 的大小没有明确给出，这里会根据初始化情况来决定。没有任何花括号，arr 按顺序初始化，即 arr[0]。[0]将是 1 和 arr[0]。a[1]将是 2。没有进一步的初始化，因此 arr 的大小为 1。正确答案是 C.

[本题小测验](https://www.geeksforgeeks.org/c-quiz-112-gq/)