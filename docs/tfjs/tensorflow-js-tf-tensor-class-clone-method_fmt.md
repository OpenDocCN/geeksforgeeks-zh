# TensorFlow.js tf.Tensor 类 clone() 方法

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-tensor-class-clone-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-tensor-class-clone-method/)

`TensorFlow.js` 是一个开源库，用于在 `Javascript` 中创建机器学习模型，允许用户直接在浏览器中运行模型。

`tf.clone()` 是在类 `tf.Tensor` 中定义的函数。它被用来创建张量的复制品。

## 语法

```
tf.clone( values )
```

## 参数

*   `values`: 它可以是值的张量或值的数组。

## 返回值

返回包含与 `values` 相同元素的 `Tensor`。

## 示例 1: 输入参数值作为张量

### Javascript

```
// Dynamic loading the "@tensorflow/tfjs" module
const tf = require('@tensorflow/tfjs');

//Creating a tensor
var values = tf.tensor([1, 2, 3, 4, 5, 6, 7]);

// Printing the colne of a tensor
tf.clone(values).print()
```

### 输出

```
Tensor
    [1, 2, 3, 4, 5, 6, 7]
```

## 示例 2: 将参数值输入为值数组

### Javascript

```
// Dynamic loading the "@tensorflow/tfjs" module
const tf = require('@tensorflow/tfjs');

//Creating a tensor
var values = [1, 2, 3, 4, 5, 6, 7];

// Printing the colne of a tensor
tf.clone(values).print()
```

### 输出

```
Tensor
    [1, 2, 3, 4, 5, 6, 7]
```

参考: [https://js.tensorflow.org/api/latest/#tf.Tensor.clone](https://js.tensorflow.org/api/latest/#tf.Tensor.clone)