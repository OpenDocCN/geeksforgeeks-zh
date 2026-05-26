# TensorFlow.js `tf.io.moveModel()` 函数

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-io-movemodel-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-io-movemodel-function/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或节点环境中运行机器学习模型以及深度学习神经网络。

`tf.io.moveModel()` 函数用于将一个模型从一个网址移动到一个新的网址。此外，这种方法有利于在存储介质内部（即在同一种记录介质内）或在两种存储介质之间（即在不同种记录介质之间）的移动。

## 语法

```
tf.io.moveModel(sourceURL, destURL)
```

## 参数

*   `sourceURL`：是规定的移动源 URL。它属于字符串类型。
*   `destURL`：是所述的移动目的地 URL。它属于字符串类型。

## 返回值

返回 `ModelArtifactsInfo` 的承诺。

## 示例 1

*   在两个不同的存储介质之间移动。
*   使用 `logSigmoid` 作为激活函数，`localStorage` 和 `IndexedDB` 作为存储介质。

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating model
const mymodel = tf.sequential();

// Calling add() method
mymodel.add(tf.layers.dense(
     {units: 3, inputShape: [20], activation: 'logSigmoid'}));

// Calling save() method with a storage medium
await mymodel.save('localstorage://display/command/mymodel');

// Calling moveModel() method with its parameters
await tf.io.moveModel(
     'localstorage://display/command/mymodel',
     'indexeddb://display/command/mymodel1');

// Calling listModels() method and
// Printing output
console.log(await tf.io.listModels());
```

### 输出

```
{
  "localstorage://demo/manage/model1": {
    "dateSaved": "2021-06-24T11:53:05.626Z",
    "modelTopologyType": "JSON",
    "modelTopologyBytes": 613,
    "weightSpecsBytes": 126,
    "weightDataBytes": 44
  },
  "localstorage://demo/management/model2": {
    "dateSaved": "2021-06-24T11:53:33.384Z",
    "modelTopologyType": "JSON",
    "modelTopologyBytes": 613,
    "weightSpecsBytes": 126,
    "weightDataBytes": 44
  },
  "localstorage://demo/management/model": {
    "dateSaved": "2021-06-24T11:53:26.006Z",
    "modelTopologyType": "JSON",
    "modelTopologyBytes": 613,
    "weightSpecsBytes": 126,
    "weightDataBytes": 44
  },
  "localstorage://demo/managemen/model1": {
    "dateSaved": "2021-06-24T11:52:29.368Z",
    "modelTopologyType": "JSON",
    "modelTopologyBytes": 611,
    "weightSpecsBytes": 124,
    "weightDataBytes": 44
  },
  "indexeddb://demo/management/model1": {
    "dateSaved": "2021-06-24T13:02:20.265Z",
    "modelTopologyType": "JSON",
    "modelTopologyBytes": 614,
    "weightSpecsBytes": 126,
    "weightDataBytes": 44
  },
  "indexeddb://display/command/mymodel": {
    "dateSaved": "2021-06-24T18:50:50.602Z",
    "modelTopologyType": "JSON",
    "modelTopologyBytes": 613,
    "weightSpecsBytes": 126,
    "weightDataBytes": 252
  },
  "indexeddb://display/command/mymodel1": {
    "dateSaved": "2021-06-24T18:55:00.803Z",
    "modelTopologyType": "JSON",
    "modelTopologyBytes": 613,
    "weightSpecsBytes": 126,
    "weightDataBytes": 252
  },
  "indexeddb://example/command/mymodel": {
    "dateSaved": "2021-06-24T12:33:06.208Z",
    "modelTopologyType": "JSON",
    "modelTopologyBytes": 613,
    "weightSpecsBytes": 126,
    "weightDataBytes": 1428
  }
}
```

## 示例 2

*   在相似的存储介质内部移动。
*   使用 `prelu` 作为激活函数，`localStorage` 作为存储介质，并使用 `JSON.stringify` 以字符串格式返回输出。

### JavaScript

```
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating model
const mymodel = tf.sequential();

// Calling add() method
mymodel.add(tf.layers.dense(
     {units: 1, inputShape: [7], activation: 'prelu'}));

// Calling save() method with a storage medium
await mymodel.save('localstorage://display/command/mymodel1');

// Calling moveModel() method with its parameters
await tf.io.moveModel(
     'localstorage://display/command/mymodel1',
     'localstorage://display/command/mymodel2');

// Calling listModels() method and
// Printing output
console.log(JSON.stringify(await tf.io.listModels()));
```

### 输出

```
{
    "localstorage://demo/manage/model1": {
        "dateSaved": "2021-06-24T11:53:05.626Z",
        "modelTopologyType": "JSON",
        "modelTopologyBytes": 613,
        "weightSpecsBytes": 126,
        "weightDataBytes": 44
    },
    "localstorage://demo/managemen/model1": {
        "dateSaved": "2021-06-24T11:52:29.368Z",
        "modelTopologyType": "JSON",
        "modelTopologyBytes": 611,
        "weightSpecsBytes": 124,
        "weightDataBytes": 44
    },
    "localstorage://demo/management/model2": {
        "dateSaved": "2021-06-24T11:53:33.384Z",
        "modelTopologyType": "JSON",
        "modelTopologyBytes": 613,
        "weightSpecsBytes": 126,
        "weightDataBytes": 44
    },
    "localstorage://demo/management/model": {
        "dateSaved": "2021-06-24T11:53:26.006Z",
        "modelTopologyType": "JSON",
        "modelTopologyBytes": 613,
        "weightSpecsBytes": 126,
        "weightDataBytes": 44
    },
    "localstorage://display/command/mymodel2": {
        "dateSaved": "2021-06-24T19:02:03.367Z",
        "modelTopologyType": "JSON",
        "modelTopologyBytes": 612,
        "weightSpecsBytes": 125,
        "weightDataBytes": 32
    },
    "indexeddb://demo/management/model1": {
        "dateSaved": "2021-06-24T13:02:20.265Z",
        "modelTopologyType": "JSON",
        "modelTopologyBytes": 614,
        "weightSpecsBytes": 126,
        "weightDataBytes": 44
    },
    "indexeddb://display/command/mymodel": {
        "dateSaved": "2021-06-24T18:50:50.602Z",
        "modelTopologyType": "JSON",
        "modelTopologyBytes": 613,
        "weightSpecsBytes": 126,
        "weightDataBytes": 252
    },
    "indexeddb://display/command/mymodel1": {
        "dateSaved": "2021-06-24T18:59:17.435Z",
        "modelTopologyType": "JSON",
        "modelTopologyBytes": 612,
        "weightSpecsBytes": 125,
        "weightDataBytes": 32
    },
    "indexeddb://example/command/mymodel": {
        "dateSaved": "2021-06-24T12:33:06.208Z",
        "modelTopologyType": "JSON",
        "modelTopologyBytes": 613,
        "weightSpecsBytes": 126,
        "weightDataBytes": 1428
    }
}
```

**参考：** [https://js.tensorflow.org/api/latest/#io.moveModel](https://js.tensorflow.org/api/latest/#io.moveModel)