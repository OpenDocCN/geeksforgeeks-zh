# TensorFlow.js TF.mirrorPad() 函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-mirrorpad-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-mirrorpad-function/)

TensorFlow.js 是一个由谷歌开发的开源库，用于在浏览器或 Node.js 环境中运行机器学习模型以及深度学习神经网络。

`tf.mirrorPad()` 函数用于借助镜像填充来填充给定的张量输入。此外，该方法支持 `pad` 的 *反射* 和 *对称* 模式。

## 语法

```javascript
tf.mirrorPad(x, paddings, mode)
```

## 参数

*   `x`: 要填充的输入张量，可以是 `tf.Tensor`、`TensorLike` 或数组。
*   `paddings`: 一个长度为 `R`（张量的秩）的数组。其中，所有元素形成长度为 2 的元组，即 `ints [padBefore, padAfter]`，指定张量每个维度的填充程度。在 *反射* 填充模式中，填充部分应排除末端；而在 *对称* 填充模式中，填充部分不应排除末端。它属于数组类型。
*   `mode`: 指定填充模式，即 `'reflect'` 或 `'symmetric'`。它是字符串类型。

## 注意

*   首先，如果输入张量是 `[4, 5, 6]` 并且填充是 `[[0, 1]]`，那么在 *反射* 填充模式下的输出将是 `[4, 5, 6, 5]`，在 *对称* 填充模式下的输出将是 `[4, 5, 6, 6]`。
*   其次，如果填充模式为 `'reflect'`，则 `paddings[d][0]` 和 `paddings[d][1]` 不得高于 `x.shape[d] - 1`；而如果填充模式为 `'symmetric'`，则 `paddings[d][0]` 和 `paddings[d][1]` 不得高于 `x.shape[d]`。

## 返回值

返回一个 `tf.Tensor` 对象。

## 示例 1

### JavaScript

```javascript
// 导入 tensorflow.js 库
import * as tf from "@tensorflow/tfjs"

// 定义输入张量
const y = tf.tensor1d([4, 5, 6]);

// 定义填充和填充模式
const padding = [[0, 1]];
const mode = 'reflect';

// 调用 tf.mirrorPad() 方法
var res = tf.mirrorPad(y, padding, mode);

// 打印输出
res.print();
```

### 输出

```
Tensor
    [4, 5, 6, 5]
```

## 示例 2

### JavaScript

```javascript
// 导入 tensorflow.js 库
import * as tf from "@tensorflow/tfjs"

// 调用 tf.mirrorPad() 方法并打印输出
tf.mirrorPad(tf.tensor(
    [2.4, 6.8, 9.3, 5.3]),
    [[0, 2]], 'symmetric').print();
```

### 输出

```
Tensor
    [2.4000001, 6.8000002, 9.3000002,
    5.3000002, 5.3000002, 9.3000002]
```

## 参考

[https://js.tensorflow.org/api/latest/#mirrorPad](https://js.tensorflow.org/api/latest/#mirrorPad)