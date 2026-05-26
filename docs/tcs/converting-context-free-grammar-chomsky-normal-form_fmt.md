# 将上下文无关语法转换为乔姆斯基范式

> 原文: [https://www.geeksforgeeks.org/converting-context-free-grammar-chomsky-normal-form/](https://www.geeksforgeeks.org/converting-context-free-grammar-chomsky-normal-form/)

## 先决条件
[简化上下文无关语法](https://www.geeksforgeeks.org/simplifying-context-free-grammars/)

## 乔姆斯基范式（CNF）的定义
如果所有生成规则满足以下条件之一，则上下文无关语法（`CFG`）处于乔姆斯基范式（`CNF`）中：
*   生成终端的非终端（例如：`X->x`）
*   产生两个非终端的非终端（例如：`X->YZ`）
*   开始生成符号 `ε`（例如：`S-> ε`）

考虑以下语法：
```
G1 = {S->a, S->AZ, A->a, Z->z} 
G2 = {S->a, S->aZ, Z->a}
```
语法 `G1` 在 `CNF` 中，因为其产生规则满足 `CNF` 指定的规则。但是，语法 `G2` 不在 `CNF` 中，因为产生规则 `S->aZ` 包含后跟非终端的终端，不满足为 `CNF` 指定的规则。

**注：**
*   对于给定的语法，可以有多个 `CNF`。
*   `CNF` 产生的语言与 `CFG` 生成的语言相同。
*   `CNF` 被用作许多 `CFG` 算法的预处理步骤，如 `CYK` 算法（隶属算法）、自底向上解析器等。
*   为了生成长度为 `n` 的字符串 `w`，需要在 `CNF` 中进行 `2n-1` 次产生或步骤。
*   任何语言中没有 `ε` 的上下文无关文法都有一个等价的 `CNF`。

## 如何将 CFG 转换成 CNF？

### 第一步：消除开始符号在 RHS 的出现
如果开始符号 `S` 出现在语法中任何产品的 `RHS` 处，则创建一个新的产生式：
```
S0 -> S
```
其中 `S0` 是新的开始符号。

### 第二步：消除无效、单位和无用的产生式
如果 `CFG` 包含无效、单位或无用的产生规则，则将其消除。你可以参考[这篇文章来消除这些类型的产生规则](https://www.geeksforgeeks.org/simplifying-context-free-grammars/)。

### 第三步：从 RHS 中消除混合的终端与非终端
如果终端与其他终端或非终端一起存在，则从 `RHS` 中删除终端。例如，产生规则 `X -> xY` 可以分解为：
```
X -> ZY
Z -> x
```

### 第四步：消除 RHS 中多于两个非终端的产生式
例如，产生规则 `X -> XYZ` 可以分解为：
```
X -> PZ
P -> XY
```

## 示例：将 CFG 转换为 CNF
考虑给定的语法 `G1`：
```
S → ASB
A → aAS|a|ε 
B → SbS|A|bb
```

### 第一步
当开始符号 `S` 出现在 `RHS` 上时，我们将创建一个新的产生规则 `S0 -> S`。因此，语法将变成：
```
S0->S
S → ASB
A → aAS|a|ε 
B → SbS|A|bb
```

### 第二步
由于语法包含空产生 `A -> ε`，将其从语法中移除会产生：
```
S0->S
S → ASB|SB
A → aAS|aS|a 
B → SbS| A|ε|bb
```
现在，它创建了零产生 `B-> ε`，将其从语法中移除会产生：
```
S0->S
S → AS|ASB| SB| S
A → aAS|aS|a 
B → SbS| A|bb
```
现在，它创建了单位产生 `B->A`，将其从语法中移除会产生：
```
S0->S
S → AS|ASB| SB| S
A → aAS|aS|a 
B → SbS|bb|aAS|aS|a
```
此外，从语法中删除单位产生 `S0->S` 会产生：
```
S0-> AS|ASB| SB| S
S → AS|ASB| SB| S
A → aAS|aS|a 
B → SbS|bb|aAS|aS|a
```
此外，从语法中删除单位产生 `S->S` 和 `S0->S` 会产生：
```
S0-> AS|ASB| SB
S → AS|ASB| SB
A → aAS|aS|a 
B → SbS|bb|aAS|aS|a
```

### 第三步
在产生规则 `A -> aAS |aS` 和 `B -> SbS|aAS|aS` 中，终端 `a` 和 `b` 存在于 `RHS` 上，且未单独终止。将它们从 `RHS` 中移除：
```
S0-> AS|ASB| SB
S → AS|ASB| SB
A → XAS|XS|a
B → SYS|bb|XAS|XS|a
X →a
Y→b
```
此外，`B->bb` 不能成为 `CNF` 的一部分，将其从语法中删除会产生：
```
S0-> AS|ASB| SB
S → AS|ASB| SB
A → XAS|XS|a
B → SYS|VV|XAS|XS|a
X → a
Y → b
V → b
```

### 第四步
在产生式规则 `S0 -> ASB` 中，`RHS` 有两个以上的符号，将其从语法中移除会产生：
```
S0-> AS|PB| SB
S → AS|ASB| SB
A → XAS|XS|a
B → SYS|VV|XAS|XS|a
X → a
Y → b
V → b
P → AS
```
同样，`S->ASB` 有两个以上的符号，将其从语法中删除会产生：
```
S0-> AS|PB| SB
S → AS|QB| SB
A → XAS|XS|a
B → SYS|VV|XAS|XS|a
X → a
Y → b
V → b
P → AS
Q → AS
```
类似地，`A->XAS` 有两个以上的符号，从语法中去掉它会产生：
```
S0-> AS|PB| SB
S → AS|QB| SB
A → RS|XS|a
B → SYS|VV|XAS|XS|a
X → a
Y → b
V → b
P → AS
Q → AS
R → XA
```
类似地，`B->SYS` 有两个以上的符号，将其从语法中删除会产生：
```
S0 -> AS|PB| SB
S → AS|QB| SB
A → RS|XS|a
B → TS|VV|XAS|XS|a
X → a
Y → b
V → b
P → AS
Q → AS
R → XA
T → SY
```
同样，`B->XAS` 有两个以上的符号，把它从语法中去掉会产生：
```
S0-> AS|PB| SB
S → AS|QB| SB
A → RS|XS|a
B → TS|VV|US|XS|a
X → a
Y → b
V → b
P → AS
Q → AS
R → XA
T → SY
U → XA
```
这是给定语法所需的 `CNF`。