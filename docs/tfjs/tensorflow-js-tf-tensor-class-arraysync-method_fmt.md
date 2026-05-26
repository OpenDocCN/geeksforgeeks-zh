# TensorFlow.js tf.Tensor 类 arraySync() 方法

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-tensor-class-arraysync-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-tensor-class-arraysync-method/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或 Node.js 环境中运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，并且可以直接在浏览器或 Node.js 中使用 ML。

`tf.Tensor` 类的 `arraySync()` 方法用于将张量数据作为嵌套数组返回。

**语法:**

```
arraySync()
```

**参数:** 不接受任何参数。

**返回值:** 返回 `number[]`。

**示例 1:** 创建二维张量。

## JavaScript

```
const a = tf.tensor2d([[0, 1], [2, 3]])

console.log(a.arraySync())
```

**输出:**

```
[[0, 1], [2, 3]]
```

**示例 2:**

## JavaScript

```
console.log(tf.tensor([1, 3, 5, 4, 2]).arraySync())
```

**输出:**

```
[1, 3, 5, 4, 2]
```

**参考:** [https://js.tensorflow.org/api/latest/#tf.Tensor.arraySync](https://js.tensorflow.org/api/latest/#tf.Tensor.arraySync)