# 语法分析中的第一组

> 原文: [https://www.geeksforgeeks.org/first-set-in-syntax-analysis/](https://www.geeksforgeeks.org/first-set-in-syntax-analysis/)

语法符号 `X` 的 `FIRST(X)` 是从 `X` 开始推导所能得到的一组终结符。

## 规则：计算 `FIRST` 集

1.  如果 `X` 是一个终结符，那么 `FIRST(X) = {X}`。
2.  如果 `X -> ε` 是一个产生式规则，那么将 `ε` 加入 `FIRST(X)`。
3.  如果 `X -> Y1 Y2 Y3 ... Yn` 是一个产生式：
    1.  `FIRST(X) = FIRST(Y1)`
    2.  如果 `FIRST(Y1)` 包含 `ε`，那么 `FIRST(X) = { FIRST(Y1) - ε } ∪ { FIRST(Y2) }`
    3.  如果对于所有的 `i`（从 1 到 n-1），`FIRST(Yi)` 都包含 `ε`，那么 `FIRST(Yi)` 也会被加入到 `FIRST(X)` 中。

## 例 1

```
产生式规则
E  -> TE’
E’ -> +T E’|Є
T  -> F T’
T’ -> *F T’ | Є
F  -> (E) | id

FIRST 集
FIRST(E) = FIRST(T) = { ( , id }
FIRST(E’) = { +, Є }
FIRST(T) = FIRST(F) = { ( , id }
FIRST(T’) = { *, Є }
FIRST(F) = { ( , id }
```

## 例 2

```
产生式规则
S -> ACB | Cbb | Ba
A -> da | BC
B -> g | Є
C -> h | Є

FIRST 集
FIRST(S) = FIRST(ACB) U FIRST(Cbb) U FIRST(Ba)
         = { d, g, h, b, a, Є}
FIRST(A) = { d } U FIRST(BC) 
         = { d, g, h, Є }
FIRST(B) = { g , Є }
FIRST(C) = { h , Є }
```

## 注意

1.  上面使用的语法是上下文无关语法（`CFG`）。大多数编程语言的语法都可以用 `CFG` 来指定。
2.  `CFG` 的形式是 `A-> B`，其中 `A` 是一个非终结符，`B` 可以是一组语法符号（即终结符和非终结符）。

在下一篇文章“编译器设计中的跟随集”中，我们将看到如何计算跟随集。

本文由 [**瓦伊巴夫巴派**](https://disqus.com/by/vaibhav2992/) 编撰。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。