# TensorFlow.js

## tf.data.Dataset.skip()方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-data-dataset-skip-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-data-dataset-skip-method/)

TensorFlow.js 是谷歌正在开发的一个开源库，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`tf.data.Dataset.skip()`方法用于创建一个跳过该数据集中初始元素计数的数据集。

**语法：**

```
skip(count)
```

**参数：** 该方法具有如上所述的单个参数，描述如下：

*   `count`：它是一个张量输入，其中应该跳过该数据集的元素数量以形成新的数据集。当`count`大于该数据集的大小时，新数据集将不包含任何元素。当`count`未定义或为负时，它会跳过整个数据集。

**返回值：** 返回 `tf.data.Dataset`。

以下示例演示了 `tf.data.Dataset.skip()`方法：

**例 1：**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining input elements
const a = 
  tf.data.array([4, 5, 6, 7, 8, 9]).skip(3);
await a.forEachAsync(e => console.log(e));
```

**输出：**

```
7
8
9
```

**例 2：**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining input elements
const a = 
  tf.data.array([4, 5, 6, 7, 8, 9]).skip(4);
await a.forEachAsync(e => console.log(e));
```

**输出：**

```
8
9
```

**参考：** [https://js.tensorflow.org/api/latest/#tf.data.Dataset.skip](https://js.tensorflow.org/api/latest/#tf.data.Dataset.skip)