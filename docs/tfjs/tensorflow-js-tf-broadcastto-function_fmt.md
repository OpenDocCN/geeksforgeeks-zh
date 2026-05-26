# TensorFlow.js `tf.broadcastTo()`函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-broadcastto-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-broadcastto-function/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`broadcastTo()`函数用于将数组循环到 NumPy 风格的一致模型。

**注意：**

*   这里，张量的形状等于从末尾到开头的广播形状。只要张量形状的长度与广播形状相同，1 就是张量形状的前缀。
*   在这种情况下，`input.shape[i]` 等于 `shape[i]`，那么第 `(i+1)` 个轴与之前的广播一致；在这种情况下，`input.shape[i]` 等于 1 加上 `shape[i]` 等于 N，那么输入张量将被此轴覆盖 *n* 次。

## 语法

```
tf.broadcastTo(x, shape)
```

## 参数

*   `x`：输入张量，可以是 `tf.Tensor` 类型或数组。
*   `shape`：指定要广播到的形状。

## 返回值

返回 `tf.Tensor` 对象。

## 示例

### 示例 1

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining tensor input elements
const y = tf.tensor1d([1, 2, 3, 4]);

// Calling broadcastTo() method and
// Printing output
tf.broadcastTo(y, [1, 4]).print();
```

**输出：**

```
Tensor
     [[1, 2, 3, 4],]
```

### 示例 2

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling broadcastTo() method and
// Printing output
tf.broadcastTo(tf.tensor1d([3.6, 5.8, 3.7, 1.4, 9.3, 10.5]), 
                         [1, 6]).print();
```

**输出：**

```
Tensor
     [[3.5999999, 5.8000002, 3.7, 1.4, 9.3000002, 10.5],]
```

**参考：** [https://js.tensorflow.org/api/latest/#broadcastTo](https://js.tensorflow.org/api/latest/#broadcastTo)