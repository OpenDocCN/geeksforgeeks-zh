# 使用函数依赖找到属性闭包和候选键

> 原文: [https://www.geeksforgeeks.org/finding-attribute-closure-and-candidate-keys-using-functional-dependencies/](https://www.geeksforgeeks.org/finding-attribute-closure-and-candidate-keys-using-functional-dependencies/)

## 什么是功能依赖？

如果对 `X` 具有相同值的两个元组对 `Y` 也具有相同值，即 `X` 唯一确定 `Y`，则关系中的函数依赖 `X->Y` 成立。

在表 1 给出的员工关系中，

*   FD `E-ID->E-NAME` 成立，因为每个 `E-ID` 都有一个唯一的 `E-NAME` 值。
*   FD `E-ID->E-CITY`、`E-CITY->E-STATE` 也成立。
*   FD `E-NAME->E-ID` **不成立**，因为 `E-NAME` 'John' 不是唯一确定 `E-ID` 的。有 2 个 `E-ID` 对应约翰（`E001` 和 `E003`）。

**员工** T2】

| **<u>E-ID</u>** | **E-NAME** | **E-CITY** | **E-STATE** |
| --- | --- | --- | --- |
| E001 | 约翰 | 德里 | 德里 |
| E002 | 玛丽 | 德里 | 德里 |
| E003 | 约翰 | 无聊死了 | U.P |

**表 1**

表 1 中给出的员工关系的功能描述集为：

```
{E-ID->E-NAME, E-ID->E-CITY, E-ID->E-STATE, E-CITY->E-STATE}
```

## 平凡与非平凡的函数依赖关系

平凡的函数依赖关系是一种在关系中始终成立的关系。

```
X->Y will always hold if X ⊇ Y
```

在上面给出的示例中，`{E-ID, E-NAME}->E-ID` 是一个微不足道的函数依赖项，并且将一直保持，因为 `{E-ID, E-NAME} ⊃ {E-ID}`。从表中还可以看到 `{E-ID, E-NAME}` 的每个值，`E-ID` 的值都是唯一的，所以 `{E-ID, E-NAME}` 在功能上决定了 `E-ID`。

如果一个函数依赖不是平凡的，它被称为**非平凡函数依赖**。非平凡函数依赖在关系中可能成立，也可能不成立。例如；`E-ID->E-NAME` 是一个非平凡的函数依赖，在上述关系中成立。

## 功能依赖的属性

让 `X`、`Y` 和 `Z` 是关系 `R` 中的属性集。函数依赖有几个性质一直存在于 `R` 中，也称为阿姆斯特朗公理。

1.  **反身性**：如果 `Y` 是 `X` 的子集，那么 `X → Y`。例如；让 `X` 代表 `{E-ID, E-NAME}`，`Y` 代表 `{E-ID}`。`{E-ID, E-NAME}->E-ID` 该关系为真。
2.  **增强**：如果 `X → Y`，那么 `XZ → YZ`。例如：让 `X` 代表 `{E-ID}`，`Y` 代表 `{E-NAME}`，`Z` 代表 `{E-CITY}`。由于 `{E-ID}->E-NAME` 对于关系为真，所以 `{E-ID, E-CITY}->{E-NAME, E-CITY}` 也将为真。
3.  **及物性**：如果 `X → Y` 和 `Y → Z`，那么 `X → Z`。例如；让 `X` 代表 `{E-ID}`，`Y` 代表 `{E-CITY}`，`Z` 代表 `{E-STATE}`。由于 `{E-ID}->{E-CITY}` 和 `{E-CITY}->{E-STATE}` 对于关系是真的，所以 `{E-ID}->{E-STATE}` 也将是真的。
4.  **属性闭包**：功能上依赖于属性 `A` 的属性集称为 `A` 的属性闭包，可以表示为 `A⁺`。

## 寻找 A 的属性闭包的步骤

给定关系 `R` 的 `FD` 集，属性闭包集 `S` 就是 `A` 的集

1.  把 `A` 加到 `S`。
2.  递归地添加属性，这些属性在功能上可以从集合 `S` 的属性中确定，直到完成。

从表 1 来看，财务数据是

**给定 `R( <u>E-ID</u> ，E-NAME，E-CITY，E-STATE)`**

```
FDs = { E-ID->E-NAME, E-ID->E-CITY, E-ID->E-STATE, E-CITY->E-STATE }
```

`E-ID` 的属性闭包可以计算为：

1.  将 `E-ID` 添加到集合 `{E-ID}`。
2.  添加可以从集合的任何属性派生的属性。在这种情况下，`E-NAME` 和 `E-CITY`、`E-STATE` 可以从 `E-ID` 衍生。所以这些也是结束的一部分。
3.  因为还有另一个属性需要从 `E-ID` 中导出。所以结果是：

```
(E-ID)⁺ = {E-ID, E-NAME, E-CITY, E-STATE }
```

同样的，

```
(E-NAME)⁺ = {E-NAME}
(E-CITY)⁺ = {E-CITY, E-STATE}
```

## 示例：找到给定 FDs 的属性闭包

**给定 `R(ABCDE) = {AB->C，B->D，C->E，D->A}`**

为了找到 `(B)⁺`，我们将使用各种 `FDs` 在集合中添加属性，如下表所示。

| 闭包中添加的属性 | 使用的 FD |
| --- | --- |
| {B} | 平凡 |
| {B, D} | B->D |
| {B, D, A} | D->A |
| {B, D, A, C} | AB->C |
| {B, D, A, C, E} | C->E |

*   我们可以找到 `(C, D)⁺`：把 `C` 和 `D` 加到集合中（琐碎），然后 `E` 用 `(C->E)`，然后 `A` 用 `(D->A)`，集合就变成了。

```
(C,D)⁺ = {C,D,E,A}
```

*   同样，我们可以通过在集合中添加 `B` 和 `C` 来找到 `(B, C)⁺`（琐碎），然后 `D` 使用 `(B->D)`，然后 `E` 使用 `(C->E)`，然后 `A` 使用 `(D->A)`，集合变成

```
(B,C)⁺ = {B,C,D,E,A}
```

## 候选键

候选关键字是关系的最小属性集，可用于唯一识别元组。例如，表 1 中给出的雇员关系的每个元组可以由 `E-ID` 唯一标识，并且它也是最小的。所以它将是关系的候选键。

候选键可以是也可以不是主键。

## 超级键

超级键是一个关系的**组属性**，可以用来唯一识别一个元组。例如，表 1 中给出的雇员关系的每个元组可以由 `E-ID` 或 `(E-ID, E-NAME)` 或 `(E-ID, E-CITY)` 或 `(E-ID, E-STATE)` 等唯一标识。所有这些都是员工关系的超级关键。

```
Note: A candidate key is always a super key but vice versa is not true.
```

## 使用 FD 集寻找关系的候选键和超键

属性集的属性闭包是关系的所有属性的集合，称为关系的超键。例如，表 1 中显示的员工关系具有以下功能描述集。

**`{E-ID->E-NAME，E-ID->E-CITY，E-ID->E-STATE，E-CITY->E-STATE}`**

让我们计算不同属性集的属性闭包：

```
(E-ID)⁺ = {E-ID, E-NAME,E-CITY,E-STATE}
(E-ID,E-NAME)⁺ = {E-ID, E-NAME,E-CITY,E-STATE}
(E-ID,E-CITY)⁺ = {E-ID, E-NAME,E-CITY,E-STATE}
(E-ID,E-STATE)⁺ = {E-ID, E-NAME,E-CITY,E-STATE}
(E-ID,E-CITY,E-STATE)⁺ = {E-ID, E-NAME,E-CITY,E-STATE}
(E-NAME)⁺ = {E-NAME}
(E-CITY)⁺ = {E-CITY,E-STATE}
```

As `(E-ID)⁺`、`(E-ID, E-NAME)⁺`、`(E-ID, E-CITY)⁺`、`(E-ID, E-STATE)⁺`、`(E-ID, E-CITY, E-STATE)⁺` 给出关系 `EMPLOYEE` 的所有属性集合。所有这些都是关系的超级钥匙。

属性闭包为关系所有属性集合的**最小属性集**称为关系候选键。如上图所示，`(E-ID)⁺` 是关系所有属性的集合，而且是最小的。所以 `E-ID` 将是候选人的关键。另一方面 `(E-ID, E-NAME)⁺` 也是所有属性的集合，但它不是最小的，因为它的子集 `(E-ID)⁺` 等于所有属性的集合。所以 `(E-ID, E-NAME)` 不是候选关键字。

***

Sonal Tuteja 撰写的文章。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论。