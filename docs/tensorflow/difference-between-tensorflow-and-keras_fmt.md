# TensorFlow 和 Keras 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-tensorflow-and-keras/](https://www.geeksforgeeks.org/difference-between-tensorflow-and-keras/)

`TensorFlow` 和 `Keras` 都是数据科学领域中著名的机器学习模块。在本文中，我们将看看这些库的优点、缺点和区别。

## TensorFlow

`TensorFlow` 是一个机器学习的开源平台，也是一个用于机器学习应用的符号数学库。

### TensorFlow 的优势：

对于给定的数据，`TensorFlow` 比任何其他顶级平台都有更好的图形表示。

*   `TensorFlow` 的优势在于它确实支持并使用了许多后端软件，如图形用户界面和专用集成电路。
*   说到社区支持，`TensorFlow` 已经最好了。
*   `TensorFlow` 还有助于调试图的子部分。
*   与其他平台相比，`TensorFlow` 表现出了更好的性能。
*   易于扩展，因为它可以自由添加自定义块来构建新的想法。

### TensorFlow 的缺点：

*   `TensorFlow` 不是专门为 `Windows` 操作系统设计的，但它是为 `Linux` 等其他操作系统设计的，但是 `TensorFlow` 可以在 `Python` 包安装程序 (`pip`) 的帮助下安装在 `Windows` 中。
*   与同类型的其他平台相比，`TensorFlow` 的速度较慢。
*   为了更好地理解 `TensorFlow`，用户必须具备微积分的基础知识。
*   `TensorFlow` 不支持 `OpenCL`。

## Keras

这是一个开源的神经网络库，运行在神经网络或 `TensorFlow` 之上。它被设计成用户使用起来既快捷又方便。它是一个有用的库，可以构建我们想要的任何深度学习算法。

### Keras 的优势：

*   `Keras` 是研究神经网络模型的最佳平台。
*   `Keras` 的 `API` 用户友好，初学者很容易理解。
*   `Keras` 的优势在于它可以选择任何支持它的库作为它的后端支持。
*   `Keras` 提供各种预训练模型，帮助用户进一步改进用户正在设计的模型。
*   说到社区支持，`Keras` 最喜欢堆栈溢出。

### Keras 的劣势：

*   `Keras` 的主要缺点是它是一个低级应用程序编程接口。
*   当涉及到一些模型的设计时，很少有预先训练好的模型是 `Keras` 不太支持的。
*   `Keras` 库给出的错误对用户没有太大帮助。

### TensorFlow 和 Keras 的区别：

| S.No | TensorFlow | Keras |
| --- | --- | --- |
| 1. | `TensorFlow` 是用 `C++`、`CUDA`、`Python` 编写的。 | `Keras` 是用 `Python` 写的。 |
| 2. | `TensorFlow` 用于大型数据集和高性能模型。 | `Keras` 通常用于小数据集。 |
| 3. | `TensorFlow` 是一个同时提供高级和低级 `API` 的框架。 | `Keras` 是一个高级 `API`。 |
| 4. | `TensorFlow` 用于高性能模型。 | `Keras` 用于低性能型号。 |
| 5. | 在 `TensorFlow` 中，执行调试会导致复杂性。 | 在 `Keras` 框架中，调试简单网络的要求很低。 |
| 6. | `TensorFlow` 架构复杂，不容易使用。 | `Keras` 架构简单，使用方便。 |
| 7. | `TensorFlow` 是由谷歌大脑团队开发的。 | `Keras` 是由 `François Chollet` 在 `ONEIROS` 项目的研究工作中开发的。 |