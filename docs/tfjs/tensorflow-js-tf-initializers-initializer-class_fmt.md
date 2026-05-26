# TensorFlow.js tf.initializers.Initializer 类

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-initializer-class/](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-initializer-class/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。`tf.initializers.Initializer()`类用于扩展序列化、可序列化的类。它是*初始化器*的基类。

这个类包含 15 个内置函数，如下所示：

*   `tf.initializers.Initializer` 类 [`constant()`](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-constant-method/) 函数
*   `tf.initializers.Initializer` 类 [`glorotNormal()`](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-glorotnormal-function/) 函数
*   `tf.initializers.Initializer` 类 [`glorotUniform()`](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-glorotuniform-function/) 函数
*   `tf.initializers.Initializer` 类 [`heNormal()`](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-henormal-function/) 函数
*   `tf.initializers.Initializer` 类 [`heUniform()`](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-heuniform-function/) 函数
*   `tf.initializers.Initializer` 类 [`identity()`](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-identity-function/) 函数
*   `tf.initializers.Initializer` 类 [`leCunNormal()`](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-lecunnormal-function/) 函数
*   `tf.initializers.Initializer` 类 [`leCunUniform()`](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-lecununiform-function/) 函数
*   `tf.initializers.Initializer` 类 [`ones()`](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-ones-function/) 函数
*   `tf.initializers.Initializer` 类 [`orthogonal()`](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-orthogonal-function/) 函数
*   `tf.initializers.Initializer` 类 [`randomNormal()`](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-randomnormal-function/) 函数
*   `tf.initializers.Initializer` 类 [`randomUniform()`](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-randomuniform-function/) 函数
*   `tf.initializers.Initializer` 类 [`truncatedNormal()`](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-truncatednormal-function/) 函数
*   `tf.initializers.Initializer` 类 `varianceScaling()` 函数
*   `tf.initializers.Initializer` 类 [`zeros()`](https://www.geeksforgeeks.org/tensorflow-js-tf-initializers-zeros-function/) 函数

## 1. tf.initializers.Initializer 类 `constant()` 函数
用于生成初始化为某个常量的值。

**示例：**

```javascript
// Importing the tensorflow.js library
const tf = require("@tensorflow/tfjs")

// Use tf.initializers.constant() function
var initializer = tf.initializers.constant({ value: 7, })

// Print the value of constant
console.log(initializer);
```

**输出：**

```
Constant { value: 7 }
```

## 2. tf.initializers.Initializer 类 `glorotNormal()` 函数
它从截断正态分布中提取样本，该正态分布以 0 为中心，`stddev = sqrt(2 / (fan_in + fan_out))`。注意，`fan_in`是张量权重中的输入数，`fan_out`是张量权重中的输出数。

**示例：**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Initializing the .initializers.glorotNormal() function
console.log(tf.initializers.glorotNormal(9));

// Printing Individual gainvalues
console.log('\nIndividual values:\n');
console.log(tf.initializers.glorotNormal(9).scale);
console.log(tf.initializers.glorotNormal(9).mode);
console.log(tf.initializers.glorotNormal(9).distribution);
```

**输出：**

```
{
    "scale": 1,
    "mode": "fanAvg",
    "distribution": "normal"
}

Individual values:

fanAvg
normal
```

## 3. tf.initializers.Initializer 类 `glorotUniform()` 函数
用于从`[-limit, limit]`内的均匀分布中提取样本，其中 `limit` 为 `sqrt(6 / (fan_in + fan_out))`，其中 `fan_in` 为权重张量中的输入单位数，`fan_out` 为权重张量中的输出单位数。

**示例：**

```javascript
// Importing the tensorflow.Js library
import * as tf from "@tensorflow/tfjs"

// Initializing the .initializers.glorotUniform() function
const geek = tf.initializers.glorotUniform(7)

// Printing gain value
console.log(geek);

// Printing individual values from gain
console.log('\nIndividual values:\n');
console.log(geek.scale);
console.log(geek.mode);
console.log(geek.distribution);
```

**输出：**

```
{
  "scale": 1,
  "mode": "fanAvg",
  "distribution": "uniform"
}

Individual values:

fanAvg
uniform
```

## 4. tf.initializers.Initializer 类 `heNormal()` 函数
用于从以零为中心的截断正态分布中抽取样本，`stddev = sqrt(2 / fanIn)`在`[-limit, limit]`内，其中，`limit` 为 `sqrt(6 / fan_in)`。注意，`fanIn` 是张量权重中的输入数。

**示例：**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Initializing the .initializers.heNormal()
// function
const geek = tf.initializers.heNormal(7)

// Printing gain
console.log(geek);
console.log('\nIndividual values:\n');
console.log(geek.scale);
console.log(geek.mode);
console.log(geek.distribution);
```

**输出：**

```
{
  "scale": 2,
  "mode": "fanIn",
  "distribution": "normal"
}

Individual values:

fanIn
normal
```

## 5. tf.initializers.Initializer 类 `heUniform()` 函数
它从`[-cap, cap]`内的均匀分布中抽取样本，其中 `cap` 是 `sqrt(6 / fan_in)`。注意，`fanIn` 是张量权重中的输入数。

**示例：**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Initializing the .initializers.heUniform() function
const geek = tf.initializers.heUniform(7)

// Printing gain
console.log(geek);
console.log('\nIndividual values:\n');
console.log(geek.scale);
console.log(geek.mode);
console.log(geek.distribution);
```

**输出：**

```
{
    "scale": 2,
    "mode": "fanIn",
    "distribution": "uniform"
}

Individual values:

fanIn
uniform
```

## 6. tf.initializers.Initializer 类 `identity()` 函数
用于返回一个新的带有身份矩阵的张量对象。它只用于 2D 矩阵。

**示例：**

```javascript
// Importing the tensorflow.Js library
import * as tf from "@tensorflow/tfjs"

// Generates the identity matrix
const value=tf.initializers.identity(1.0)

// Print gain
console.log(value)
```

**输出：**

```
{
 "gain": 1
}
```

## 7. tf.initializers.Initializer 类 `leCunNormal()` 函数
用于从以零为中心的截断正态分布中提取样本，`stddev = sqrt(1 / fanIn)`。注意，`fanIn` 是张量权重中的输入数。

**示例：**

```javascript
// Importing the tensorflow.Js library
import * as tf from "@tensorflow/tfjs"

// Initializing the .initializers.leCunNormal() function
const geek = tf.initializers.leCunNormal(3)

// Printing gain
console.log(geek);
console.log('\nIndividual values:\n');
console.log(geek.scale);
console.log(geek.mode);
console.log(geek.distribution);
```

**输出：**

```
{
    "scale": 1,
    "mode": "fanIn",
    "distribution": "normal"
}

Individual values:

fanIn
normal
```

## 8. tf.initializers.Initializer 类 `leCunUniform()` 函数
它从 `cap = sqrt(3 / fanIn)` 的区间`[-cap, cap]`的均匀分布中抽取样本。注意，`fanIn` 是张量权重中的输入数。

**示例：**

```javascript
// Importing the tensorflow.Js library
import * as tf from "@tensorflow/tfjs"

// Initialising the .initializers.leCunUniform() function
console.log(tf.initializers.leCunUniform(4));

// Printing individual values from the gain
console.log("\nIndividual Values\n");
console.log(tf.initializers.leCunUniform(4).scale);
console.log(tf.initializers.leCunUniform(4).mode);
console.log(tf.initializers.leCunUniform(4).distribution);
```

**输出：**

```
{
  "scale": 1,
  "mode": "fanIn",
  "distribution": "uniform"
}

Individual Values

fanIn
uniform
```

## 9. tf.initializers.Initializer 类 `ones()` 函数
用于创建所有元素都设置为 1 的张量，或者用值 1 初始化张量。

**示例：**

```javascript
//import tensorflow.js
const tf=require("@tensorflow/tfjs")

//use tf.ones()
var GFG=tf.ones([3, 4]);

//print tensor
GFG.print()
```

**输出：**

```
Tensor
   [[1, 1, 1, 1],
    [1, 1, 1, 1],
    [1, 1, 1, 1]]
```

## 10. tf.initializers.Initializer 类 `orthogonal()` 函数
它产生一个随机正交矩阵。

**示例：**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Initializing the .initializers.orthogonal() function
let geek = tf.initializers.orthogonal(2)

// Printing gain value
console.log(geek);

// Printing individual gain value
console.log('\nIndividual values:\n');
console.log(geek.DEFAULT_GAIN);
console.log(geek.gain);
```

**输出：**

```
{
  "DEFAULT_GAIN": 1,
  "gain": 1
}

Individual values:

```

## 11. tf.initializers.Initializer 类 `randomNormal()` 函数
用于产生初始化为正态分布的随机值。

**示例：**

## JavaScript 描述语言

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Initializing the tf.initializers.randomNormal() function
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

```json
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

## TF.initializer.initializer 类：randomUniform() 函数

用于生成初始化为均匀分布的随机值。这些值在配置的最小值和最大值之间均匀分布。

**示例:**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Initializing the tf.initializers.randomUniform() function
let geek = tf.initializers.randomUniform(5)

// Printing gain value
console.log(geek);

// Printing individual gain value.
console.log('\nIndividual values:\n');
console.log(geek.DEFAULT_MINVAL);
console.log(geek.DEFAULT_MAXVAL);
console.log(geek.minval);
console.log(geek.maxval);
```

**输出:**

```json
{
  "DEFAULT_MINVAL": -0.05,
  "DEFAULT_MAXVAL": 0.05,
  "minval": -0.05,
  "maxval": 0.05
}

Individual values:

-0.05
0.05
-0.05
0.05
```

## TF.initializer.initializer 类：truncatedNormal() 函数

该函数产生初始化为截断正态分布的随机值。

**示例:**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Initializing the tf.initializers.truncatedNormal()
// function
let geek = tf.initializers.truncatedNormal(13)

// Printing gain value
console.log(geek);

// Printing individual gain value
console.log('\nIndividual values:\n');
console.log(geek.DEFAULT_MEAN);
console.log(geek.DEFAULT_STDDEV);
console.log(geek.mean);
console.log(geek.stddev);
```

**输出:**

```json
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

## TF.initializer.initializer 类：varianceScaling() 函数

可以根据砝码形状调整刻度。使用分布= NORMAL 的值，从中心为 0 的截断正态分布中抽取样本，`stddev = sqrt(scale / n)`。

**示例:**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Initializing the tf.initializers.varianceScaling()
// function
let geek = tf.initializers.varianceScaling(33)

// Printing gain value
console.log(geek);

// Printing individual gain value.
console.log('\nIndividual values:\n');
console.log(geek.scale);
console.log(geek.mode);
console.log(geek.distribution);
```

**输出:**

```json
{
  "scale": 1,
  "mode": "fanIn",
  "distribution": "normal"
}

Individual values:

fanIn
normal
```

## TF.initializer.initializer 类：zeros() 函数

它是一个初始值设定项，用来产生初始化为零的张量。

**示例:**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling tf.initializers.zeros() function
const initializer = tf.initializers.zeros();

// Printing output
console.log(JSON.stringify(+initializer));
```

**输出:**

```json
null
```

**参考:** [https://js.tensorflow.org/api/latest/#class:initializers.Initializer](https://js.tensorflow.org/api/latest/#class:initializers.Initializer)