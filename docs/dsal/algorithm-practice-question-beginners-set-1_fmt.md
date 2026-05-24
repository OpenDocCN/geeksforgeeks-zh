# 初学者算法练习题 | 第 1 集

> 原文: [https://www.geeksforgeeks.org/algorithm-practice-question-beginners-set-1/](https://www.geeksforgeeks.org/algorithm-practice-question-beginners-set-1/)

考虑下面的 C 函数。

```c
unsigned fun(unsigned n)
{
    if (n == 0) return 1;
    if (n == 1) return 2;

    return fun(n-1) + fun(n-1);
}
```

对于忽略编译器优化的上述代码，请考虑以下问题。
a) 上面的代码是做什么的？
b) 以上代码的时间复杂度是多少？
c) 能否降低上述函数的时间复杂度？

## fun(n) 是做什么的？

在上面的代码中，`fun(n)` 等于 `2*fun(n-1)`。所以上面的函数返回 `2^n`。例如，对于 `n = 3`，它返回 `8`，对于 `n = 4`，它返回 `16`。

## fun(n) 的时间复杂度是多少？

上述函数的时间复杂度为指数级。设时间复杂度为 `T(n)`。`T(n)` 可以写成下面的递推式。这里 `C` 是一个机器相关的常数。

```
T(n) = T(n-1) + T(n-1) + C
     = 2T(n-1) + C
```

上述递推有解为 `θ(2^n)`。我们可以用递归树的方法来解决。递归树将是高度为 `n` 的二叉树，并且除了最后一层之外，每一层都将完全填满。

```
                       C
                  /        \
               C              C
            /     \         /     \
          C        C       C        C
         / \      / \     / \      / \
        .  .     .   .   .   .    .   .
        .  .     .   .   .   .    .   .
       Height of Tree is Θ(n)
```

## fun(n) 的时间复杂度可以降低吗？

降低时间复杂度的简单方法是调用一次函数，而不是调用两次。

```c
unsigned fun(unsigned n)
{
    if (n == 0) return 1;
    if (n == 1) return 2;

    return 2*fun(n-1);
}
```

上述解的时间复杂度为 `θ(n)`。设时间复杂度为 `T(n)`。`T(n)` 可以写成下面的递推式。这里 `C` 是一个机器相关的常数。

```
T(n) = T(n-1) + C
```

我们可以用递归树的方法来解决。递归树将是高度为 `n` 的倾斜二叉树（每个内部节点只有一个子节点）。

```
            C
           /
          C
         /
        C
       /
      .
    .
 Height of Tree is Θ(n)
```

使用分治技术计算幂可以进一步优化上述函数。

```c
unsigned fun(unsigned n)
{
    if (n == 0) return 1;
    if (n == 1) return 2;
    unsigned x = fun(n/2);
    return (n%2)? 2*x*x: x*x;
}
```

上述解的时间复杂度为 `θ(Logn)`。设时间复杂度为 `T(n)`。`T(n)` 可以近似写成下列递推式。这里 `C` 是一个机器相关的常数。

```
T(n) = T(n/2) + C
```

我们可以用递归树的方法来解决。递归树将是一个倾斜的二叉树（每个内部节点只有一个子节点），高度为 `Log(n)`。

```
            C
           /
          C
         /
        C
       /
      .
    .
 Height of Tree is Θ(Logn)
```

我们还可以使用按位左移运算符 `<<`。

```c
unsigned fun(unsigned n)
{
   return 1 << n;
}
```