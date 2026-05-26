# TensorFlow.js `TF.sparseFillEmptyRows()` 函数

> 哎哎哎:# t0]https://www . geeksforgeeks . org/tensorlow-js-TF-sparefilemptyrrows-function/

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。它还帮助开发人员用 JavaScript 语言开发 ML 模型，并且可以直接在浏览器或 Node.js 中使用 ML。

`TF.sparseFillEmptyRows()` 函数用于获取通过输入映射表示的输入稀疏度(索引、值、密集度)。

**语法:**

```
tf.sparseFillEmptyRows(indices, values, denseShape, defaultValue)
```

**参数:**

*   **indices:** 稀疏张量的索引。
*   **values:** 稀疏张量的值。
*   **denseShape:** 稀疏张量的形状。
*   **defaultValue:** 插入位置的默认值。

**返回值:** 返回 `tf.Tensor`

**例 1:**

## JavaScript

```
const result = tf.sparse.sparseFillEmptyRows(
    [[0, 1], [1, 2], [2, 3], [3, 4], [4, 5]],
    [0, 1, 2, 3, 4], [5, 6], -1);

result['outputIndices'].print();
result['outputValues'].print();
result['reverseIndexMap'].print();
```

**输出:**

```
Tensor
    [[0, 1],
     [1, 2],
     [2, 3],
     [3, 4],
     [4, 5]]
Tensor
    [0, 1, 2, 3, 4]
Tensor
    [0, 1, 2, 3, 4]
```

**例二:**

## JavaScript

```
const result = tf.sparse.sparseFillEmptyRows(
    [[1], [1], [4], [3], [2]],
    [4, 6, 8, 5, 3], [7, 2], -1);

console.log(result);
```

**输出:**

```
{
  "outputIndices": {
    "kept": false,
    "isDisposedInternal": false,
    "shape": [
      5,

],
    "dtype": "float32",
    "size": 5,
    "strides": [

],
    "dataId": {
      "id": 12
    },
    "id": 12,
    "rankType": "2",
    "scopeId": 2
  },
  "outputValues": {
    "kept": false,
    "isDisposedInternal": false,
    "shape": [

],
    "dtype": "float32",
    "size": 5,
    "strides": [],
    "dataId": {
      "id": 13
    },
    "id": 13,
    "rankType": "1",
    "scopeId": 2
  },
  "emptyRowIndicator": {
    "kept": false,
    "isDisposedInternal": false,
    "shape": [

],
    "dtype": "bool",
    "size": 7,
    "strides": [],
    "dataId": {
      "id": 14
    },
    "id": 14,
    "rankType": "1",
    "scopeId": 2
  },
  "reverseIndexMap": {
    "kept": false,
    "isDisposedInternal": false,
    "shape": [

],
    "dtype": "float32",
    "size": 5,
    "strides": [],
    "dataId": {
      "id": 15
    },
    "id": 15,
    "rankType": "1",
    "scopeId": 2
  }
}
```

**参考:** [`https://js.tensorflow.org/api/latest/#sparseFillEmptyRows`](https://js.tensorflow.org/api/latest/#sparseFillEmptyRows)