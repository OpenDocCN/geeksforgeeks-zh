# 代码转换器–二进制到/自格雷码

> 原文: [https://www.geeksforgeeks.org/code-converters-binary-to-from-gray-code/](https://www.geeksforgeeks.org/code-converters-binary-to-from-gray-code/)

**先决条件–** [数字系统和基数转换](https://www.geeksforgeeks.org/number-system-and-base-conversions/)

格雷码系统是一种二进制数字系统，其中每对连续的数字仅相差一位。它用于由硬件生成的二进制数的正常序列在从一个数到下一个数的转换过程中可能产生错误或模糊的应用中。
例如，系统的状态可能从 3(011)变为 4(100) as- 011 — 001 — 101 — 100。因此，当系统从初始状态变为最终状态时，读取错误状态的可能性很高。
这可能会对使用该信息的机器产生严重后果。格雷码消除了这个问题，因为在两个数字之间的任何转换过程中，只有一位改变其值。

### 将二进制转换为格雷码–

设 `b_0, b_1, b_2, and b_3` 为代表二进制数的位，其中 `b_0` 为 LSB，`b_3` 为 MSB，
设 `g_0, g_1, g_2, and g_3` 为代表二进制数格雷码的位，其中 `g_0` 为 LSB，`g_3` 为 MSB。
转换的真值表是-
![真值表](img/893ae5116201a2d82ed946847da75402.png)

为了找到相应的数字电路，我们将对每个格雷码位使用 K-Map 技术作为输出，所有二进制位作为输入。
K 线图为 `g_0`–
![](img/26eb299a8ea6f0aa574edcb82378ac93.png)
k 线图为 `g_1`–
![](img/502bd21865e009fda4150d6235c4c730.png)
k 线图为 `g_2`–
![](img/caaac122a4c2795e741bc0990558f2ab.png)
k 线图为 `g_3`–
![](img/79434d887e6edda785f3c4bbc205962a.png)

对应的最小化布尔表达式为格雷码位–
![布尔表达式](img/8ec8d9ae7904c4aed325dbf564fecb6f.png)
对应的数字电路–
![](img/5d9b7a01465d4e4eddfc9f92b53dbb7d.png)

### 将格雷码转换为二进制–

将格雷码转换回二进制可以用类似的方式完成。
设 `b_0, b_1, b_2, and b_3` 为代表二进制数的位，其中 `b_0` 为 LSB，`b_3` 为 MSB，
设 `g_0, g_1, g_2, and g_3` 为代表二进制数格雷码的位，其中 `g_0` 为 LSB，`g_3` 为 MSB。
真值表-
![真值表](img/b10241408c09b07926fad83a711e0d86.png)

使用 K-map 从格雷码中取回二进制位–`b_0`–
![](img/1d5c74cb9e5e629c40b18a20d9d35eff.png)
K-map 为 `b_1`–
![](img/afe04acd69e515eed7200b24a44ca12d.png)
K-map 为 `b_2`–
![](img/af2f93a64840adbc674fd9aa7a9308c1.png)
K-map 为 `b_3`–
![](img/0c8eb76cecade56e01f35882c3ad3b59.png)

对应的布尔表达式–
![布尔表达式](img/3e7bbdf812b93c83c69d291d841dcc03.png)

对应的数字电路–
![](img/8bfabf396528e22f2894275f56d8f21e.png)

**参考文献–**

数字设计，第五版，莫里斯·马诺和迈克尔·西莱蒂

本文由**奇拉·曼瓦尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。