# TensorFlow.js `GraphModel` 类 `save()` 方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-graphmodel-class-save-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-graphmodel-class-save-method/)

**简介：** TensorFlow.js 是谷歌开发的开源库，用于在浏览器或 Node.js 环境下运行机器学习模型以及深度学习神经网络。

**`save()` 功能** 用于保存所述 `GraphModel` 的结构和/或权重。

**注意：**

*   `ioHandler` 是一个对象，它包含一个具有特定签名的保存方法。
*   `save` 方法控制序列数据的累积或传输，即描述模型拓扑和权重的构件（artifacts），通过特定介质（如 *本地存储*、*文件下载*、*IndexedDB*）或在 Web 浏览器中通过 HTTP 请求发送到服务器。
*   TensorFlow.js 提供了多种 `ioHandler`，例如 `tf.io.browserDownloads()`、`tf.io.browserIndexedDB()` 和 `tf.io.browserLocalStorage()`。
*   此外，此方法还允许我们应用特定类型的 `ioHandler`，例如基于 URL 的字符串方案，如 `"localstorage://"` 和 `"indexeddb://"`。

**语法：**

```javascript
save(handlerOrURL, config?)
```

**参数：**

*   **`handlerOrURL`**：`ioHandler` 的实例，或基于类似 `ioHandler` 设计的字符串 URL。类型为 `io.IOHandler | string`。
*   **`config`**：用于保存模型的选项。可选，对象类型。包含以下两个参数：
    1.  **`trainableOnly`**：指示是否仅保存模型的可训练权重，非训练权重将被忽略。类型为 `Boolean`，默认为 `false`。
    2.  **`includeOptimizer`**：指示是否存储优化器。类型为 `Boolean`，默认为 `false`。

**返回值：** 返回一个 `io.SaveResult` 的 Promise。

**例 1：**

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Defining model url
const model_Url =
'https://storage.googleapis.com/tfjs-models/savedmodel/mobilenet_v2_1.0_224/model.json';

// Calling the loadGraphModel() method
const mymodel = await tf.loadGraphModel(model_Url);

// Calling save() method
const output = await mymodel.save('downloads://mymodel');

// Printing output
console.log(output)
```

**输出：**

```json
{
  "modelArtifactsInfo": {
    "dateSaved": "2021-08-19T12:00:15.603Z",
    "modelTopologyType": "JSON",
    "modelTopologyBytes": 90375,
    "weightSpecsBytes": 15791,
    "weightDataBytes": 13984940
  }
}
```

**例 2：**

### JavaScript

```javascript
// Importing the tensorflow.js library
import * as tf from "@tensorflow/tfjs"

// Calling the loadGraphModel() method
const mymodel = await tf.loadGraphModel(
'https://storage.googleapis.com/tfjs-models/savedmodel/mobilenet_v2_1.0_224/model.json');

// Calling save() method with all its
// parameters
const output = await mymodel.save('downloads://mymodel', true, true);

// Printing output
console.log(JSON.stringify(output))
```

**输出：**

```json
{"modelArtifactsInfo":{"dateSaved":"2021-08-19T12:05:35.906Z",
"modelTopologyType":"JSON","modelTopologyBytes":90375,
"weightSpecsBytes":15791,"weightDataBytes":13984940}}
```

**参考：** [https://js.tensorflow.org/api/latest/#tf.GraphModel.save](https://js.tensorflow.org/api/latest/#tf.GraphModel.save)