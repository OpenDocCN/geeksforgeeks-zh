# 计算机组织|指令格式(零、一、二、三地址指令)

> 原文：[https://www.geeksforgeeks.org/computer-organization-instruction-formats-zero-one-two-three-address-instruction/](https://www.geeksforgeeks.org/computer-organization-instruction-formats-zero-one-two-three-address-instruction/)

计算机根据提供的指令执行任务。计算机中的指令由称为字段的组组成。这些字段包含不同的信息，对于计算机来说，一切都在 0 和 1 之间，因此每个字段都有不同的意义，中央处理器根据这些意义来决定执行什么。最常见的字段有：

*   操作字段指定要执行的操作，如加法。
*   包含操作数位置的地址字段，即寄存器或存储器位置。
*   指定如何创建操作数的模式字段。

指令的长度是可变的，取决于它包含的地址数量。通常，基于地址字段的数量，CPU 组织有三种类型：

1.  单一累加器组织
2.  普通注册机构
3.  栈结构

在第一种组织中，操作是通过一个称为累加器的特殊寄存器来完成的。其次，多个寄存器用于计算目的。在第三种组织中，基于堆栈的工作操作，因此它不包含任何地址字段。不需要应用单一的组织，我们通常看到的是各种组织的混合。

根据地址的数量，指令分为：

请注意，我们将使用 `X = (A+B)*(C+D)` 表达式来展示该过程。

## 零地址指令

基于堆栈的计算机不使用指令中的地址字段。要计算一个表达式，首先要将其转换为逆波兰符号，即后缀符号。

```
Expression: X = (A+B)*(C+D)
Postfixed : X = AB+CD+*
TOP means top of stack
M[X] is any memory location
```

| 操作 | 操作数 | 栈状态 |
| :--- | :--- | :--- |
| PUSH | A | TOP = A |
| PUSH | B | TOP = B |
| ADD | | TOP = A+B |
| PUSH | C | TOP = C |
| PUSH | D | TOP = D |
| ADD | | TOP = C+D |
| MUL | | TOP = (C+D)*(A+B) |
| POP | X | M[X] = TOP |

## 一个地址指令

这使用一个隐含的累加器寄存器进行数据操作。一个操作数在累加器中，另一个在寄存器或存储单元中。隐含意味着 CPU 已经知道累加器中有一个操作数，所以不需要指定它。

```
Expression: X = (A+B)*(C+D)
AC is accumulator
M[] is any memory location
M[T] is temporary location
```

| 操作 | 操作数 | 描述 |
| :--- | :--- | :--- |
| LOAD | A | AC = M[A] |
| ADD | B | AC = AC + M[B] |
| STORE | T | M[T] = AC |
| LOAD | C | AC = M[C] |
| ADD | D | AC = AC + M[D] |
| MUL | T | AC = AC * M[T] |
| STORE | X | M[X] = AC |

## 两个地址说明

这在商用计算机中很常见。这里可以在指令中指定两个地址。与之前的一条地址指令不同，结果存储在累加器中，这里的结果可以存储在不同的位置，而不仅仅是累加器，但是需要更多的位数来表示地址。

这里目的地址也可以包含操作数。

```
Expression: X = (A+B)*(C+D)
R1, R2 are registers
M[] is any memory location
```

| 操作 | 操作数 | 描述 |
| :--- | :--- | :--- |
| MOV | R1, A | R1 = M[A] |
| ADD | R1, B | R1 = R1 + M[B] |
| MOV | R2, C | R2 = M[C] |
| ADD | R2, D | R2 = R2 + M[D] |
| MUL | R1, R2 | R1 = R1 * R2 |
| MOV | X, R1 | M[X] = R1 |

## 三个地址指令

这有三个地址字段来指定寄存器或存储器位置。创建的程序在大小上要短得多，但是每条指令的位数增加了。这些指令使程序的创建变得容易得多，但这并不意味着程序将运行得更快，因为现在指令只包含更多的信息，但每个微操作（改变寄存器的内容、在地址总线中加载地址等）都包含更多的信息，将只在一个周期内执行。

```
Expression: X = (A+B)*(C+D)
R1, R2 are registers
M[] is any memory location
```

| 操作 | 操作数 | 描述 |
| :--- | :--- | :--- |
| ADD | R1, A, B | R1 = M[A] + M[B] |
| ADD | R2, C, D | R2 = M[C] + M[D] |
| MUL | X, R1, R2 | M[X] = R1 * R2 |