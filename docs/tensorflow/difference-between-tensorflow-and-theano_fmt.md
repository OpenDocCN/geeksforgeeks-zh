# TensorFlow 和 Theano 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-tensorflow-and-theano/](https://www.geeksforgeeks.org/difference-between-tensorflow-and-theano/)

在这篇文章中，我们将比较并找出 TensorFlow 和 Theano 的区别。这两个模块都用于深度学习，并且经常根据它们的技术、受欢迎程度等进行比较。让我们看看它们之间的详细比较。

## Theano

它是一个 Python 库和优化编译器，用于操作和评估数学表达式，尤其是那些带有矩阵值的表达式。Theano 也可以被定义为 2007 年推出的科学计算库，它可以在 CPU 和 GPU 上运行。

### Theano 的优势:

*   `Keras`、`Lasagne` 和 `Blocks` 等套餐都是在 Theano 的基础上打造的。
*   Theano 是一种低级产品。
*   拥有高级模块，如 `Keras`、`Blocks`、`Lasagne` 等，使其更具实用性。

### Theano 的缺点:

*   在 `AWS` 上，它可能很复杂。
*   它可以在单个 GPU 上运行。
*   对于庞大而复杂的模型，需要大量的编译时间。
*   错误通知很复杂，这使得调试更加困难。

## TensorFlow

它是主要为机器学习程序员提供开源贡献的软件。TensorFlow 是一个符号数学库，用于机器学习应用。

### TensorFlow 的优势:

*   它适用于强化学习等算法。
*   提供图形计算抽象。
*   数据和模型的并行性是可用的。
*   它可以在各种 CPU 和 GPU 上运行。

### TensorFlow 的缺点:

*   由于它不接受矩阵运算，复制这些巨大的矩阵是一种耗时的方法。
*   与其他框架相比，它运行缓慢。
*   没有预先训练的模型可用。
*   退出程序，以 Python 加载每个新的训练批次。
*   适应性不强。
*   在大规模开发程序中，动态类型很容易出错。

## TensorFlow 和 Theano 之间的差异表

```
|   | TensorFlow | Theano |
| --- | --- | --- |
| 执行速度 | 与 Theano 相比，TensorFlow 的执行速度较慢。但是在处理需要多个 GPU 的任务的情况下，TensorFlow 更快。 | Theano 执行任务的速度比 TensorFlow 快得多。主要是那些需要单个 GPU 的任务在 Theano 会运行得更快。 |
| 技术 | TensorFlow 缺少本机 Windows 支持。它不支持 `Lasagne`。 | Theano 具有本机 Windows 支持。它还支持高级包装，如 `Lasagne`。 |
| 证明文件 | 与 Theano 相比，TensorFlow 的文档更少。 | 与 TensorFlow 相比，Theano 有更多的文档。 |
| 和睦相处 | TensorFlow 专门在 Linux、macOS、Windows 和 Android 上运行。 | Theano 跨平台运行。 |
| 流行 | TensorFlow 是著名的深度学习库之一，主要用于研究目的。 | Theano 是一个旧框架，并没有被广泛使用。 |
| 内置模型 | TensorFlow 没有任何预先训练的内置模型 | Theano 与一个名为 `Keras` 的深度学习库兼容，该库包含一些预训练的模型。 |
```

## 结论

两个框架中的接口是相同的。另一方面，TensorFlow 更容易使用，因为它附带了许多监控工具。就功能和速度而言，Theano 更好，但 TensorFlow 最适合部署。