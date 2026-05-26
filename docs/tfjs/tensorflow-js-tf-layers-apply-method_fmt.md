# TensorFlow.js TF.layers.apply()方法

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-layers-apply-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-layers-apply-method/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。

`tf.layers.apply()`方法用于执行层计算，并在我们用`Tensor`调用它时返回`Tensor`。如果我们用`SymbolicTensor`调用它，那么符号张量将为将来的执行准备层。

## 语法

```
apply(inputs, kwargs)
```

## 参数

*   `inputs`：此参数将数组保存为输入。
*   `kwargs`[可选]：它是一个可选参数，保存要传递给`call()`的附加关键字参数。

## 返回值

返回同一数据类型的张量或符号张量。

## 示例

下面的例子说明了 TensorFlow.js `tf.layers.apply()`方法：

### 示例1

```javascript
import * as tf from "@tensorflow/tfjs"

const denseLayer = tf.layers.dense({
   units: 1,
   kernelInitializer: 'ones',
   useBias: false
});

const input = tf.ones([2, 2]);
const output = denseLayer.apply(input);

// Print the output
print(output)
```

**输出：**

```
Tensor [[2], [2]]
```

### 示例2

```javascript
import * as tf from "@tensorflow/tfjs"

const denseLayer = tf.layers.dense({
   units: 1,
   kernelInitializer: 'zeros',
   useBias: false
});

const input = tf.ones([2, 2]);
const output = denseLayer.apply(input);

// Print the output
print(output)
```

**输出：**

```
Tensor [[0], [0]]
```

**参考：** [https://js.tensorflow.org/api/latest/#tf.layers.Layer.apply](https://js.tensorflow.org/api/latest/#tf.layers.Layer.apply)