# 在 scanf()中使用&，但在 printf()中不使用

> 原文:[https://www.geeksforgeeks.org/use-scanf-not-printf/](https://www.geeksforgeeks.org/use-scanf-not-printf/)

为什么在 scanf 函数的情况下需要使用' & '，而在 printf 函数的情况下不需要。

示例:

```cpp
scanf("%d %d", &a, &b);
printf("%d %d", a, b);

```

由于上面的 a 和 b 是两个变量，每个变量都分配了自己的地址，但是我们分别发送 a 和 b 的地址，而不是 a 和 b。原因是，scanf()需要修改 a 和 b 的值，但它们是 scanf()的本地值。所以为了反映主函数变量 a 和 b 的变化，我们需要传递它们的地址。我们不能简单地通过价值传递它们。
但是在 printf 函数的情况下，因为我们只打印输出控制台中变量的值，所以变量 a 和 b 的值不会发生变化。所以不需要发送他们的地址。