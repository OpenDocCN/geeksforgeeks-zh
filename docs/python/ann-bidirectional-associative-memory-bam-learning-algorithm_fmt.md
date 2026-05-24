# ANN–双向联想记忆(BAM)学习算法

> 原文: [https://www.geeksforgeeks.org/ann-bidirectional-associative-memory-bam-learning-algorithm/](https://www.geeksforgeeks.org/ann-bidirectional-associative-memory-bam-learning-algorithm/)

**先决条件:** [ANN |双向联想记忆(BAM)](https://www.geeksforgeeks.org/ann-bidirectional-associative-memory-bam/)

构建 BAM 模型有三个主要步骤。

1.  学习
2.  测试
3.  检索

在《人工神经网络|双向联想记忆》一文中，每一步都用数学公式进行了描述。

**这里用一个例子迭代说明这个学习算法。**
假设，
集合 A:输入模式

![Set A: X1, X2, X3, X4](img/ae526f05096e492ba6e2888b49e4c5e1.png "Rendered by QuickLaTeX.com")

集合 B:对应的目标模式

![Set B: Y1, Y2, Y3, Y4](img/a012e1b7c2a67ba0146ab12e7648a592.png "Rendered by QuickLaTeX.com")

***第一步:*** 这里，M(图案对数)的值为 4。
***第二步:*** 分配输入输出层的神经元。这里，输入层的神经元是 6 个，输出层是 3 个

***第三步:*** 现在，计算权重矩阵(W):

![W的计算过程](img/5be65e81412bea52d0e15338961aaf87.png "Rendered by QuickLaTeX.com")

***第四步:*** 测试 BAM 模型学习算法——对于输入模式 BAM 会返回相应的目标模式作为输出。对于每个目标模式，BAM 将返回相应的输入模式。

*   Test on input patterns (Set A) using-

![Ym = sign(W^T Xm)](img/1a53a3a09b029dde2f9afc43d6e602a2.png "Rendered by QuickLaTeX.com")

![Y1, Y2, Y3, Y4的计算结果](img/9ae0ca68e78404a1f77e5735b51d2c40.png "Rendered by QuickLaTeX.com")

*   Test on target patterns (Set B) using-

![Xm = sign(W Ym)](img/1e50c2615965586680d4d7d37013ce45.png "Rendered by QuickLaTeX.com")

![X1, X2, X3, X4的计算结果](img/90a3544e2be47f3f52ff39ab69edd7a8.png "Rendered by QuickLaTeX.com")

这里，对于每个输入模式，BAM 模型将给出正确的目标模式，对于目标模式，模型也将给出相应的输入模式。
这表示内存或模型网络中的双向关联。