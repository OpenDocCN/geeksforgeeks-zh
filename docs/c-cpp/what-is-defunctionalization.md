# 什么是去功能化

> 原文:[https://www.geeksforgeeks.org/what-is-defunctionalization/](https://www.geeksforgeeks.org/what-is-defunctionalization/)

去函数化是一种编译时转换，通过用单个一阶应用函数替换高阶函数来移除高阶函数。

这种方法最早由约翰·c·雷诺兹在 1972 年提出。约翰·c·雷诺兹的论文《高阶程序设计语言的定义解释器》就体现了这一点。他的检查是:

*   在一个给定的程序中有有限多的函数抽象，所以这些函数抽象通过一个唯一的标识符来恢复和分配。
*   在程序中，函数的每个应用程序都通过调用 apply 函数来恢复，函数标识符是第一个参数。
*   该应用函数的任务是在第一个参数上执行，然后执行指令，这由剩余参数上的函数标识符指示。

去功能化的一个困难是:

*   自由变量由函数抽象引用。在这种情况下，应该通过闭包转换或 lambda lifting 引入去功能化(这是一个重新构造程序的元过程，以便在全局范围内相互独立地定义函数)，这样，如果函数抽象有任何自由变量，那么它们将作为额外的参数传递以应用。
*   此外，如果闭包转换被保留为一级值，那么就必须表示通过构造数据结构捕获的这些绑定。

在程序中，对所有函数抽象执行，而不是只应用一个函数。为了确定在每个函数应用程序站点应该调用什么函数，有不同种类的控制流分析(包括基于类型签名的简单区别)，还有一个专门的应用函数，可以交替推荐。相反，目标语言支持通过函数指针的间接调用，这可能比基于调度的方法更有组织性和可扩展性。

**去功能化步骤:**
去功能化高阶函数有两个步骤:

1.  对于使用高阶函数并将其应用于函数的每个位置，用指定数据类型的值恢复该函数以构成该函数。这被称为“去功能化符号”。
2.  根据 HOF 的定义，如果一个函数参数被应用到任何地方，通过调用一个专用的一阶函数来恢复该应用的函数参数，该函数将解释这个参数现在代表的去函数化符号。通常，该函数被称为 **apply** ，有时被称为 **eval** 。

函数式编程思想是在去函数化的帮助下产生的。在已经具有高阶功能的语言，即功能语言中，去功能化有很大的价值。

尽管去掉了更高阶的功能，去功能化是一种将解释器机械地转换成抽象机器的方式，它也通过面向对象编程语言中的函数对象来表示函数。

**下面是 Olivier Danvy 给出的例子，翻译成 Haskell :**
下面是树数据类型:

```cpp
data Tree a = Leaf a
            | Node (Tree a) (Tree a)
```

现在，我们必须取消下面给出的程序的功能:

```cpp
cons :: a -> [a] -> [a]
cons x xs = x : xs

o :: (b -> c) -> (a -> b) -> a -> c
o f g x = f (g x)

flatten :: Tree t -> [t]
flatten t = walk t []

walk :: Tree t -> [t] -> [t]
walk (Leaf x)     = cons x
walk (Node t1 t2) = o (walk t1) (walk t2)
```

现在，为了解除上述程序的功能，我们将用 **lam** 数据类型值替换所有高阶函数(即 **o** ，这是这里唯一的高阶函数)，我们将启动**应用**函数来简化数据类型–

```cpp
data Lam a = LamCons a
           | LamO (Lam a) (Lam a)

apply :: Lam a -> [a] -> [a]
apply (LamCons x)  xs = x : xs
apply (LamO f1 f2) xs = apply f1 (apply f2 xs)

cons_def :: a -> Lam a
cons_def x  = LamCons x

o_def :: Lam a -> Lam a -> Lam a
o_def f1 f2 = LamO f1 f2

flatten_def :: Tree t -> [t]
flatten_def t = apply (walk_def t) []

walk_def :: Tree t -> Lam t
walk_def (Leaf x)     = cons_def x
walk_def (Node t1 t2) = o_def (walk_def t1) (walk_def t2)
```