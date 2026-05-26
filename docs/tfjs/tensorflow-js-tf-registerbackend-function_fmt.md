# TensorFlow.js TF.registerBackend()函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-registerbackend-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-registerbackend-function/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。

TensorFlow.js `TF.registerBackend()` 函数用于在导入模块文件时注册一个全局后端。注册的后端用于模块化构建。

**语法:**

```javascript
tf.registerBackend(name, factory, priority?)
```

**参数:**

*   `name` (字符串): 指定要注册的后端的名称。
*   `factory`: 指定后端工厂功能。这个函数返回一个后端实例或者一个实例的承诺。
*   `priority` (数字): 指定该后端的优先级。优先级更高的后端更重要。此参数的默认值为 1。

**返回值:** 返回布尔值。

**例 1:**

```javascript
// Importing the tensorflow.js library 
const tf = require("@tensorflow/tfjs");

// Try to register a 'webgl' backend
const status = tf.registerBackend("webgl")

// Print status
console.log(status)
```

**输出:**

```
true
```

**例 2:**

```javascript
// Importing the tensorflow.js library 
const tf = require("@tensorflow/tfjs");

// Try to register a 'cpu' backend
const status = tf.registerBackend("cpu")

// Print status
console.log(status)
```

**输出:**

```
false
```

**参考:** [https://js.tensorflow.org/api/latest/#registerBackend](https://js.tensorflow.org/api/latest/#registerBackend)