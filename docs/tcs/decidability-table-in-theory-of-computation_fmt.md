# 计算理论中的判定表

> 原文: [https://www.geeksforgeeks.org/decidability-table-in-theory-of-computation/](https://www.geeksforgeeks.org/decidability-table-in-theory-of-computation/)

先决条件 – [不可判定性](https://www.geeksforgeeks.org/undecidability-and-reducibility/)、[可判定和不可判定的问题](https://www.geeksforgeeks.org/theory-computation-decidable-undecidable-problems/)

将语言（或问题）识别为可判定、不可判定或部分可判定是 GATE 中非常常见的问题。有了正确的知识和丰富的经验，这个问题就很容易解决了。

如果一种语言是不可判定的，那么它就是不可判定的。不可判定的语言可能是部分可判定的语言，或者是其他不可判定的语言。如果一种语言甚至不可部分判定，那么这种语言就不存在图灵机。

在本主题中，您将看到可判定性表和学习它们的快捷方式。

两种递归可枚举语言的交集是递归可枚举的，因此是可判定的。

## 判定性表

| 问题 | `RL` | `DCFL` | `CFL` | `CSL` | `REC.L` | `REL` |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| “`w`”属于 `L` 语言吗？（即成员资格问题，其中“`w`”是任何字符串） | `D` | `D` | `D` | `D` | `D` | `UD` |
| `L = null` 吗？（即空虚问题） | `D` | `D` | `D` | `UD` | `UD` | `UD` |
| 是 `L = Σ*` ？（即完备性问题，其中 `Σ*` 是给定字母表上所有可能字符串的集合） | `D` | `D` | `UD` | `UD` | `UD` | `UD` |
| `L1 = L2` 吗？（即平等问题。`L1` 和 `L2` 是同一类型的语言。） | `D` | `D` | `UD` | `UD` | `UD` | `UD` |
| `L1` 是 `L2` 的子集吗？（即子集问题） | `D` | `UD` | `UD` | `UD` | `UD` | `UD` |
| `L2 ∩ L1` 是否为空？ | `D` | `UD` | `UD` | `UD` | `UD` | `UD` |
| `L` 到底是不是有限的？（即有限性问题） | `D` | `D` | `D` | `UD` | `UD` | `UD` |
| `L` 的补集是不是同类型的语言？ | `D` | `D` | `UD` | `D` | `D` | `UD` |
| 两种语言的交集是不是同类型的？ | `D` | `UD` | `UD` | `D` | `D` | `D` |
| `L` 是不是正则语言？（`L` 是任何语言。） | `D` | `D` | `UD` | `UD` | `UD` | `UD` |

## 缩写说明

在上表中，

```
'RL' implies Regular language.
'CFL' implies Context free language.
'DCFL' implies deterministic context free language.
'CSL' implies Context sensitive language.
'REC.L' implies Recursive language.
'REL' implies Recursive enumerable language.
'D' implies that the problem is decidable.
'UD' implies that the problem is undecidable.
```

## 注释

1.  **正则语言 (`RL`)**：它对所有问题都是可判定的。
2.  **上下文无关语言 (`CFL`)**：对于空性问题、有限性问题、隶属性问题是可判定的。
3.  **上下文有关语言 (`CSL`) 和递归语言 (`REC.L`)**：两者对于成员问题都是可判定的，对于“`L` 的补集是不是同类型的语言？”以及“两种语言的交集是否属于同一类型？”也是可判定的。
4.  **递归可枚举语言 (`REL`)**：可判定为“两种语言的交集是不是同类型？”。
5.  **确定性上下文无关语言 (`DCFL`)** 在 **上下文无关语言 (`CFL`)** 基础上，额外可判定“`L` 的补集是不是同类型的语言？”以及“`L` 是正则语言吗？”。