# TensorFlow.js `tf.initializers.randomNormal()` 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-randomnormal-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-randomnormal-function/)

`TensorFlow.js` 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，并且可以直接在浏览器或 Node.js 中使用 ML。

函数的作用是：产生随机值，这些随机值被初始化为正态分布。

语法：
```
tf.initializers.randomNormal(arguments)
```

**参数:**

`Parameter` 是一个包含三个键值的对象，如下所列：
1.  `Average`：是要生成的随机值的平均值。
2.  `stddev`：是要生成的随机值的标准差。
3.  `Seed`：它是随机数生成器的种子。

**返回值:** 返回一个初始化器对象。

**例 1:**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Initializing the .initializers.randomNormal() function
let geek = tf.initializers.randomNormal(3)

// Printing gain value
console.log(geek);

// Printing individual gain value.
console.log('\nIndividual values:\n');
console.log(geek.DEFAULT_MEAN);
console.log(geek.DEFAULT_STDDEV);
console.log(geek.mean);
console.log(geek.stddev);
```

**输出:**

```
{
  "DEFAULT_MEAN": 0,
  "DEFAULT_STDDEV": 0.05,
  "mean": 0,
  "stddev": 0.05
}

Individual values:

0.05

0.05
```

**例 2:**

```javascript
// Importing the tensorflow.Js library
import * as tf from "@tensorflow/tfjs"

// Defining the input value
const inputValue = tf.input({shape:[4]});

// Initializing tf.initializers.randomNormal() function.
const funcValue = tf.initializers.randomNormal(3)

// Creating dense layer 1
const dense_layer_1 = tf.layers.dense({
    units: 5,
    activation: 'relu',
    kernelInitialize: funcValue
});

// Creating dense layer 2
const dense_layer_2 = tf.layers.dense({
    units: 7,
    activation: 'softmax'
});

// Output
const outputValue = dense_layer_2.apply(
    dense_layer_1.apply(inputValue)
);

// Creation the model.
const model = tf.model({
    inputs: inputValue,
    outputs: outputValue
});

// Predicting the output.
model.predict(tf.ones([2, 4])).print();
```

**输出:**

```
Tensor
    [[0.1165049, 0.2952721, 0.1367277, 0.1689866, 
      0.0897676, 0.0964029, 0.0963382],
     [0.1165049, 0.2952721, 0.1367277, 0.1689866, 
      0.0897676, 0.0964029, 0.0963382]]
```

**参考资料:** [https://js.tensorflow.org/api/3.6.0/#initializers.randomNormal](https://js.tensorflow.org/api/3.6.0/#initializers.randomNormal)