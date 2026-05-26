# TensorFlow.js tf.LayersModel 类 save() 方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-layersmodel-class-save-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-layersmodel-class-save-method/)

TensorFlow.js 是一个开源库，由谷歌开发，用于在浏览器或 Node 环境中运行机器学习模型以及深度学习神经网络。

`save()` 功能用于保存所述*图层模型*的结构和/或权重。

**注意：**

*   `IOHandler` 是一个对象，它具有关于指定确切签名的保存方法。
*   `save` 方法控制顺序数据的累积或传输，即描述模型拓扑和权重的工件，通过特定媒体（如本地存储文件、文件下载、Web 浏览器中的索引数据库以及对服务器的 HTTP 请求）进行存储或传输。
*   TensorFlow 管理器、`browserDownload()`、`tf.io.browserLocalStorage`。
*   此外，此方法还允许我们应用特定类型的 `IOHandler`，例如基于 URL 的字符串技术，如 `"localstorage://"` 和 `"indexeddb://"`。

**语法：**

```
save(handlerOrURL, config?)
```

**参数：**

*   **`handlerOrURL`：** `IOHandler` 的声明实例，或基于设计支持 `IOHandler` 的类似 URL 的字符串。其类型为 `io.IOHandler | string`。
*   **`config`：** 保存模型的选项。它是可选的，属于对象类型。它有两个参数，如下所示：
    1.  **`trainableOnly`：** 它声明是否仅保存模型的可训练权重并忽略未训练的权重。它属于布尔类型，默认值为 `false`。
    2.  **`includeOptimizer`：** 指示是否存储优化器。它属于布尔类型，默认值为 `false`。

**返回值：** 返回一个 `io.SaveResult` 的 Promise。

**例 1：**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating a model
const model = tf.sequential(
     {layers: [tf.layers.dense({units: 2, inputShape: [2]})]});

// Calling save() method
const res = await model.save('localstorage://mymodel');

// Printing output
console.log(res)
```

**输出：**

```
{
  "modelArtifactsInfo": {
    "dateSaved": "2021-08-23T09:53:28.198Z",
    "modelTopologyType": "JSON",
    "modelTopologyBytes": 612,
    "weightSpecsBytes": 125,
    "weightDataBytes": 24
  }
}
```

**例 2：**

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Creating a model
const model = tf.sequential(
     {layers: [tf.layers.dense({units: 2, inputShape: [2]})]});

// Calling save() method
const res = await model.save('localstorage://mymodel', true, true);

// Printing output
console.log(JSON.stringify(res))
```

**输出：**

```
{"modelArtifactsInfo":{"dateSaved":"2021-08-23T09:55:33.044Z",
"modelTopologyType":"JSON","modelTopologyBytes":612,
"weightSpecsBytes":125,"weightDataBytes":24}}
```

**参考：** [https://js.tensorflow.org/api/latest/#tf.LayersModel.save](https://js.tensorflow.org/api/latest/#tf.LayersModel.save)