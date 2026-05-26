# Tensorflow.js tf.tidy()函数

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-tidy-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-tidy-function/)

Tensorflow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`tf.tidy()`函数用于执行给定的函数，即 `fn`，一旦终止，它将清除由所述函数 `fn` 分配的所有中间张量，不包括由 `fn` 返回的张量。在此，`fn` 不应产生承诺。然而，返回的输出可能是一个复杂的对象。

**注意:**

*   此方法有助于防止内存泄漏。通常，将调用包装在 `tf.tidy()` 函数中可以自动清理内存。
*   然而，变量不会在 `tidy()` 函数中被清除。如果要释放变量，可以使用 `tf.disposeVariables()` 或立即在变量上调用 `dispose()` 方法。

**语法:**

```javascript
tf.tidy(nameOrFn, fn?)
```

**参数:**

*   `nameOrFn`: 要执行的函数或指定的名称。如果提供了名称，则第二个参数必须是一个函数。如果调试模式已开启，函数的调度和内存使用将使用给定的名称进行，并在控制台中显示。它可以是字符串或函数类型。
*   `fn`: 要执行的指定函数。它是可选的，属于函数类型。

**返回值:** 返回 `void`、`number`、`string`、`TypedArray`、`tf.Tensor`、`tf.Tensor[]` 或 `{[key: string]: tf.Tensor | number | string}`。

**例 1:**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling tidy() method
const res = tf.tidy(() => {

// Calling scalar() method
   const x = tf.scalar(3);

// Calling sqrt() function
   const y = tf.sqrt(5);

// Calling square() method
   const z = y.square();

// Calling sub() method 
  return z.sub(x);
});

// Printing output
res.print();
```

**输出:**

```
Tensor
    0.7639320225002102
```

**例 2:**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling tidy() method
const res = tf.tidy(() => {

// Calling sin() method
   const op = tf.sin(45);

// Printing number of tensors inside tidy
   // Using memory() method
   console.log('number of tensors inside tidy: '
      + tf.memory().numTensors);

// Calling sqrt() method 
  return op.sqrt();
});

// Printing number of tensors outside tidy
   // Using memory() method
   console.log('number of tensors outside tidy: '
      + tf.memory().numTensors);

// Printing output
res.print();
```

**输出:**

```
number of tensors inside tidy: 1
number of tensors outside tidy: 1
Tensor
    0.9224448204040527
```

**参考:** [https://js.tensorflow.org/api/latest/#tidy](https://js.tensorflow.org/api/latest/#tidy)