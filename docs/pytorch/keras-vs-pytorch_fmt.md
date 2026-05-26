# Keras 与 PyTorch

> 原文链接：[https://www.geeksforgeeks.org/keras-vs-pytorch/](https://www.geeksforgeeks.org/keras-vs-pytorch/)

## 简介

`Keras` 和 `PyTorch` 是两个最强大的开源机器学习库。

`Keras` 是一个基于 `Python` 的开源库，用于深度学习（用于神经网络）。它可以运行在 `TensorFlow`、微软 `CNTK` 或 `Theano` 之上。理解和使用非常简单，适合快速实验。`Keras` 模型既可以在中央处理器上运行，也可以在图形处理器上运行。

`PyTorch` 是一个开源的机器学习库，由脸书的 `AI` 研究小组开发。它可以与 `Python` 和 `C++` 集成。它之所以受欢迎，是因为它高效的内存使用和轻松调试神经网络的能力。

## 对比

让我们看看 `Keras` 和 `PyTorch` 的区别。

| 序号 | Keras | PyTorch |
| :--- | :--- | :--- |
| 1. | `Keras` 发布于 2015 年 3 月。 | `PyTorch` 发布于 2016 年 10 月。 |
| 2. | `Keras` 拥有高级 `API`。 | `PyTorch` 的 `API` 级别较低。 |
| 3. | `Keras` 的速度相对较慢。 | `PyTorch` 的速度比 `Keras` 更快，适用于高性能场景。 |
| 4. | `Keras` 结构简单，可读性更高，使用更方便。 | 然而，由于其复杂的架构，`PyTorch` 的可读性非常低。 |
| 5. | `Keras` 的社区支持较弱。 | 而 `PyTorch` 拥有更强大的社区支持。 |
| 6. | 由于速度慢，`Keras` 多用于小型数据集。 | 而 `PyTorch` 是大型数据集和高性能的首选。 |
| 7. | 由于存在计算垃圾，在 `Keras` 中调试很困难。 | 在 `PyTorch` 中调试更容易、更快速。 |
| 8. | `Keras` 提供静态计算图。 | 而 `PyTorch` 提供动态计算图。 |
| 9. | `Keras` 的后端包括 `TensorFlow`、`Theano` 和 微软 `CNTK`。 | 但 `PyTorch` 没有独立的后端实现。 |