# TensorFlow.js TF.truncatedNormal()函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-truncatednormal-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-truncatednormal-function/)

Tensorflow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`tf.truncatedNormal()`函数用于查找`tf.tensor`以及根据截断正态分布计算的值。此外，这里作为输出产生的值在规定的平均值和标准偏差的支持下遵循正态分布，排除那些相对于平均值大于 2 个标准偏差的值，这些值被丢弃并再次选择。

## 语法

```
tf.truncatedNormal(shape, mean?, stdDev?, dtype?, seed?)
```

## 参数

*   `shape`: 它是一个数组，包含描述输出张量形状的整数，类型为`number[]`。
*   `mean`: 是正态分布的规定平均值，为`number`类型。
*   `stdDev`: 是正态分布的规定标准差，`number`类型。
*   `dtype`: 是返回的输出张量的规定数据类型，可以是`float32`或`int32`类型。
*   `seed`: 是在随机数发生器中有帮助的所述种子，并且是`number`类型。

## 返回值

返回`tf.tensor`对象。

## 例 1

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling truncatedNormal() method and
// Printing output
tf.truncatedNormal([3, 4]).print();
```

### 输出

```
Tensor
    [[-0.0277713, -0.4777073, -0.3911407, 1.85613   ],
     [-0.0667888, -0.0867875, 0.8295102 , -0.5933844],
     [0.5160138 , 0.7871808 , 0.6818511 , 1.2177598 ]]
```

## 例 2

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining shape
var sh = [3, 2];
var mean = 4;
var st_dev = 5;
var dtyp = 'int32';

// Calling truncatedNormal() method
var res = tf.truncatedNormal(sh, mean, st_dev, dtyp);

// Printing output
res.print();
```

### 输出

```
Tensor
    [[-1, -5],
     [4 , 4 ],
     [11, 2 ]]
```

## 参考

[https://js.tensorflow.org/api/latest/#truncatedNormal](https://js.tensorflow.org/api/latest/#truncatedNormal)