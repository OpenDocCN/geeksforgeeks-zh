# 构造有限的机器，将“1”作为子串“a”每次出现的输出

> 原文：[https://www.geeksforgeeks.org/construction-of-finite-machines-to-prints-1-as-the-output-for-every-occurrence-of-a-as-a-substring/](https://www.geeksforgeeks.org/construction-of-finite-machines-to-prints-1-as-the-output-for-every-occurrence-of-a-as-a-substring/)

## 前提
[美利和摩尔机器](https://www.geeksforgeeks.org/mealy-and-moore-machines/) [美利机器和摩尔机器](https://www.geeksforgeeks.org/difference-between-mealy-machine-and-moore-machine/)的区别在本文中，我们将看到一些有输出的有限自动机的设计，即摩尔和美利机器。

## 问题
构造机器，该机器将`{a，b}`上的所有字符串集作为输入，并将“a”作为子字符串的每次出现打印“1”作为输出。
假设，

```
Ε = {a, b} and 
Δ = {0, 1}  
```

其中`ε`和`δ`分别是输入和输出字母表。

## 说明
所需的摩尔机构造如下：
![](img/783569ba97a1159d27afb68d416f9a3b.png)

在上图中，初始状态`X`在获得`b`作为输入时，它保持自身状态，并打印`0`作为输出，在获得`a`作为输入时，它转换到状态`Y`，并打印`1`作为输出。状态`Y`在获取`a`作为输入时，它保持自身状态，并打印`1`作为输出，在获取`b`作为输入时，它返回状态`X`，并打印`0`作为输出。

因此，最后上面的摩尔机器可以很容易地打印“1”作为输出，得到“a”作为输入子串。

上面的 Moore 机器将`{a，b}`上的所有字符串集合作为输入，并计算子串`a`的数量，即在获取`a`作为子串时，它给出`1`作为输出，因此在计算`1`的数量时，我们可以计算子串`a`的数量。

现在我们需要把上面摩尔机的过渡图转换成等价的 Mealy 机过渡图。

## 从摩尔机到美利机的转换
所需转换的步骤如下：

### Step-1: Formation of State Transition Table of the above Moore machine
![](img/b03c035a001a17b6d1bf6632c7ac8ece.png)
在上表中，状态`X`和`Y`位于第一列，当获得`a`作为输入时，它们分别转换到第二列中的`Y`和`Y`状态，当获得`b`作为输入时，它们分别转换到第三列中的`X`和`X`状态。

在`δ`下的第四列中，有第一列状态的相应输出。在表格中，箭头（`→`）表示初始状态。

### Step-2: Formation of Transition Table for Mealy machine from above Transition Table of Moore machine
下面的转换表将借助上表及其条目，通过使用第一列状态的相应输出并将其相应地放置在第二列和第三列中来形成。
![](img/139b1686f5168c2f1516f6ef63b2862b.png)
在上表中，第一列中的状态如`X`，当获得`a`作为输入时，它转到状态`Y`并给出`1`作为输出，当获得`b`作为输入时，它转到状态`X`并给出`0`作为输出，第一列中的其余状态依此类推。在表格中，箭头（`→`）表示初始状态。

### 第三步: Formation of State Transition Diagram for Mealy machine
最后我们可以借助上面的转换表来形成 Mealy 机器的状态转换图。
所需的图表如下所示：
![](img/5fc3e61842be99bd133fb38b57fdd3cc.png)
以上 Mealy 机器将`{a，b}`上的所有字符串集作为输入，并计算子字符串`a`的数量，即在获取`a`作为子字符串时，它给出`1`作为输出，因此在计算`1`的数量时，我们可以计算子字符串`a`的数量。

**注意：**当从摩尔转换到米莱机时，摩尔和米莱机的状态数保持不变，但是在米莱到摩尔转换的情况下，它给出的状态数并不相同。