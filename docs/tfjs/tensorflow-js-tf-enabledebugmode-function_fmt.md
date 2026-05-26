# TensorFlow.js TF.enableDebugMode() 函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-enabledebugmode-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-enabledebugmode-function/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`tf.enableDebugMode()` 函数用于启用调试模式，该模式将记录关于每个执行的内核的数据，即内核实现的跳动时间，包括结果张量的等级、大小以及形状。

**注意:**

*   调试模式将极大地降低软件速度，因为它会将每个操作的最终结果下载到 CPU 中，因此不能在生产环境中使用。
*   调试模式不会影响内核性能的时间序列数据，因为此处的下载时间不计入内核性能时间。

## 语法

```
tf.enableDebugMode()
```

## 参数

此方法不接受任何参数。

## 返回值

返回 `void`。

## 例 1

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling enableDebugMode() method
await tf.enableDebugMode();

// Setting prod mode of the
// environment
tf.env().set('PROD', false);

// Printing output
console.log(tf.env().flags);
```

**输出:**

```
{
  "IS_BROWSER": true,
  "IS_NODE": false,
  "DEBUG": true,
  "CPU_HANDOFF_SIZE_THRESHOLD": 128,
  "PROD": false
}
```

## 例 2

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling enableDebugMode() method
await tf.enableDebugMode();

// Setting debug mode of the environment
tf.env().set("DEBUG", !0)

// Setting textures of the environment
tf.env().set('WEBGL_FORCE_F16_TEXTURES', true);

// Calling ready() method
await tf.ready();

// Printing output
console.log(tf.env().features);
```

**输出:**

```
{
  "IS_BROWSER": true,
  "IS_NODE": false,
  "DEBUG": true,
  "CPU_HANDOFF_SIZE_THRESHOLD": 128,
  "PROD": true,
  "WEBGL_FORCE_F16_TEXTURES": true,
  "WEBGL_VERSION": 2,
  "HAS_WEBGL": true
}
```

## 参考

[https://js.tensorflow.org/api/latest/#enableDebugMode](https://js.tensorflow.org/api/latest/#enableDebugMode)