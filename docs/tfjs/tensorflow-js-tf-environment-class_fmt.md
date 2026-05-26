# TensorFlow.js tf.Environment 类

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-environment-class/](https://www.geeksforgeeks.org/tensorflow-js-tf-environment-class/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或 Node 环境中运行机器学习模型和深度学习神经网络。`tf.Environment()` 类包括评估标志和注册平台。它每次都像全局单例一样使用，并且可以从 `tf.env()` 函数中恢复。

这个环境类包含五个内置函数，如下所示：

*   `tf.Environment.disposeVariables()` 函数
*   `tf.Environment.enableDebugMode()` 函数
*   `tf.Environment.enableProdMode()` 函数
*   `tf.Environment.engine()` 函数
*   `tf.Environment.env()` 函数

## tf.Environment.disposeVariables() 函数

`tf.Environment.disposeVariables()` 函数用于处理存储在后端引擎中的每个变量。

**例 1：**

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Declaring a variable
var x = tf.tensor([1, 2, 3, 4]);

// Calling disposeVariables() method
tf.disposeVariables();

// Printing output
console.log("Variables disposed.")
```

**输出：**

```
Variables disposed.
```

## tf.Environment.enableDebugMode() 函数

`tf.Environment.enableDebugMode()` 函数用于启用调试模式，该模式将注册关于每个执行的内核的数据，即内核实现的跳动时间，包括秩、大小以及结果张量的形状。

**例 2：**

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling enableDebugMode() method
await tf.enableDebugMode();

// Setting prod mode of the environment
tf.env().set('PROD', false);

// Printing output
console.log(tf.env().flags);
```

**输出：**

```javascript
{
  "IS_BROWSER": true,
  "IS_NODE": false,
  "DEBUG": true,
  "CPU_HANDOFF_SIZE_THRESHOLD": 128,
  "PROD": false
}
```

## tf.Environment.enableProdMode() 函数

`tf.Environment.enableProdMode()` 函数用于启用生产模式，以取消支持生产的精确约束。

**例 3：**

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling enableProdMode() method
await tf.enableProdMode();

// Setting debug mode of the environment
tf.env().set('DEBUG', false);

// Printing output
console.log(tf.env().flags);
```

**输出：**

```javascript
{
  "IS_BROWSER": true,
  "IS_NODE": false,
  "DEBUG": false,
  "CPU_HANDOFF_SIZE_THRESHOLD": 128,
  "PROD": true,
  "WEBGL_VERSION": 2,
  "HAS_WEBGL": true,
  "WEBGL_CHECK_NUMERICAL_PROBLEMS": false,
  "IS_TEST": false,
  "WEBGL_CPU_FORWARD": true,
  "WEBGL_MAX_TEXTURE_SIZE": 16384,
  "WEBGL_FORCE_F16_TEXTURES": true,
  "WEBGL_RENDER_FLOAT32_CAPABLE": true,
  "WEBGL_RENDER_FLOAT32_ENABLED": true,
  "WEBGL_FLUSH_THRESHOLD": -1,
  "WEBGL_PACK": true,
  "WEBGL_LAZILY_UNPACK": true,
  "WEBGL_DELETE_TEXTURE_THRESHOLD": -1,
  "WEBGL_PACK_BINARY_OPERATIONS": true,
  "WEBGL_USE_SHAPES_UNIFORMS": false,
  "WEBGL_PACK_UNARY_OPERATIONS": true,
  "WEBGL_DOWNLOAD_FLOAT_ENABLED": true,
  "WEBGL_CONV_IM2COL": true,
  "WEBGL_PACK_DEPTHWISECONV": true,
  "WEBGL_MAX_TEXTURES_IN_SHADER": 16,
  "WEBGL_PACK_ARRAY_OPERATIONS": true
}
```

## tf.Environment.engine() 函数

`tf.Environment.engine()` 函数是用来返回全局引擎，保存每一个张量的路径以及后端。

**例 4：**

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling engine() and startScope() method
tf.engine().startScope();

// Calling ones() method
const res = tf.ones([200, 250]);

// Printing output
console.log(res);
```

**输出：**

```
Tensor
    [[1, 1, 1, ..., 1, 1, 1],
     [1, 1, 1, ..., 1, 1, 1],
     [1, 1, 1, ..., 1, 1, 1],
     ...,
     [1, 1, 1, ..., 1, 1, 1],
     [1, 1, 1, ..., 1, 1, 1],
     [1, 1, 1, ..., 1, 1, 1]]
```

## tf.Environment.env() 函数

`tf.Environment.env()` 函数用于返回当前环境，即一个全局实体。此外，环境对象包括评估的属性值以及动态平台。

**例 5：**

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling env() and getBool() method along with its parameter
const res = tf.env().getBool('WEBGL_RENDER_FLOAT32_ENABLED');

// Printing output
console.log(res);
```

**输出：**

```
true
```

**参考：** [https://js.tensorflow.org/api/latest/#class:Environment](https://js.tensorflow.org/api/latest/#class:Environment)