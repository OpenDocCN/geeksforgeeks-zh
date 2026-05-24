# 计算 N 维数组中元素的地址

> 原文: [https://www.geeksforgeeks.org/calculating-the-address-of-an-element-in-an-n-dimensional-array/](https://www.geeksforgeeks.org/calculating-the-address-of-an-element-in-an-n-dimensional-array/)

## N 维数组

[N 维数组](https://www.geeksforgeeks.org/multidimensional-arrays-c-cpp/)基本上是数组的[数组](https://www.geeksforgeeks.org/arrays-in-c-cpp/)。由于 **1-D** 阵列被识别为单个索引，因此 **2-D** 阵列使用两个索引来识别，类似地，**N 维**阵列使用 **N** 索引来识别。一个[多维](https://www.geeksforgeeks.org/multidimensional-arrays-c-cpp/)数组声明如下:

```
NDA S1 S2 S3 …….. SN;
```

**解说:**

*   这里，`NDA` 是 N 维数组的名字。它可以是任何有效的[标识符](https://www.geeksforgeeks.org/difference-between-keyword-and-identifier/)名称。
*   在上面的语法中，`S1`，`S2`，`S3`……`SN` 表示 **N** 尺寸的最大尺寸。
*   假设所有维度的下限都为零。
*   以上[数组](https://www.geeksforgeeks.org/how-to-initialize-array-of-objects-with-parameterized-constructors-in-c/)声明为整数数组。它也可以是整数以外的任何有效的[数据类型](https://www.geeksforgeeks.org/c-data-types/)。

## N 维数组的地址计算

### 假设

*   N 维最大尺寸为 `S1` `S2` `S3` …… `SN` 的 N 维阵 `NDA`。
*   需要计算其地址的元素具有索引 `I1`，`I2`，`I3`，……..`IN` 分别为。
*   数组索引的下限可能不为零。例如，考虑以下数组 `T`: `T[-5…5][2…9][14…54][-9…-2]`。

### 解说

*   在上面的数组 `T` 中，索引的下限不是零。
*   所以现在数组的索引的大小是不同的，可以用下面的公式计算:

> **upper bound – lower bound + 1**

*   所以，这里 `S1` = 5 – (-5) + 1 = 11。同样，`S2` = 8，`S3` = 41，`S4` = 8。

地址计算的下限为 `t1`，`t2`，`t3` …… `tN`。存储数组元素有两种方法:

*   行主序
*   列主序

### 列主公式

```
NDA[I1][I2]…[IN] 的地址 = BAd + W * [(…((EN * SN-1 + EN-1) * SN-2 + … + E3) * S2 + E2) * S1 + E1]
```

*   `BAd` 表示数组的**基地址**。
*   `W` 代表数组的**宽度**，即数组中每个元素占用的存储单元数。
*   另外，`Ei` 由 **`Ei = Ii – ti`** 给出，其中 `Ii` 和 `ti` 分别是计算出的指标(需要确定的数组元素的指标)和下限。

### 行主公式

```
NDA[I1][I2]…[IN] 的地址 = BAd + W * [((…(E1 * S2 + E2) * S3 + E3) * S4 ….. + EN-1) * SN + EN]
```

## 学习公式最简单的方法

**对于行主序:** 如果宽度= 5，内部顺序为 `E1 * S2 + E2 * S3 + E3 * S4 + E4 * S5 + E5`。如果宽度= 3，按照顺序找出图案，并按照四个基本步骤计算任意宽度的公式:

*   写出内部序列。
*   除第一项外，在每个 `E` 后放上右括号。所以对于宽度= 5，它变成:

> `E1 * S2 + E2) * S3 + E3) * S4 + E4) * S5 + E5)`

*   首先放好所有的左括号。

> `(((E1 * S2 + E2) * S3 + E3) * S4 + E4) * S5 + E5)`

*   在公式中加入基址和宽度。

对于**列主序**来说，方法是相似的，但是内部序列的模式与行主序模式相反。

**对于列主序:** 如果宽度=5，内部顺序为 **`E5 * S4 + E4 * S3 + E3 * S2 + E2 * S1 + E1`**。

## 例

我们取一个多维数组 `A[10][20][30][40]`，基地址 `1200`。任务是找到元素 `A[1][3][5][6]` 的地址。

这里，`BAd` = 1200，`W` = 4。
`S1` = 10，`S2` = 20，`S3` = 30，`S4` = 40

因为没有给出下限，所以下限假设为零。
`E1` = 1 – 0 = 1；
`E2` = 3 – 0 = 3；
`E3` = 5 – 0 = 5；
`E4` = 6 – 0 = 6。

任何技术(行主序或列主序)都可以用于计算答案(除非特别说明)。
应用行主公式，直接将公式写成:

```
A[1][3][5][6] = 1200 + 4 * (((1 * 20 + 3) * 30 + 5) * 40 + 6)
```

计算过程:

```
= 1200 + 4 * ((23 * 30 + 5) * 40 + 6)
= 1200 + 4 * (695 * 40 + 6)
= 1200 + 4 * (27800 + 6)
= 1200 + 4 * 27806
= 1200 + 111224
= 112424
```