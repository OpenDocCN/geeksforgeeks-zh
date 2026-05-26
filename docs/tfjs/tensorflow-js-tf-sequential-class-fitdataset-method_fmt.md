# TensorFlow.js tf.sequential类的fitDataset()方法

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-sequential-class-fitdataset-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-sequential-class-fitdataset-method/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或节点环境中运行机器学习模型和深度学习神经网络。TensorFlow.js `tf.sequential`类的`fitDataset()`方法用于使用数据集对象训练模型。

## 语法

```
model.fitDataset(dataset, args);
```

## 参数

该方法包含以下参数：

*   `dataset`：是一个包含输入值的数据集。它可以是一个原始数据集、一个数组或一个对象。
*   `args`：它包含以下值：
    *   `epochs`：是训练模型期间在训练数据集上的总轮数。它是一个整数值。
    *   `batchSize`：定义每个批次的大小。它的值取决于批次大小，随着批次大小的增加，其大小也会减小。
    *   `verbose`：它有助于显示每个轮次的进度。如果值为 0——意味着在`fit()`调用期间不打印任何消息。如果值为 1——在 Node.js 中，它将打印一个进度条。在浏览器中，它不显示任何操作。值 1 是默认值。值 2 尚未实现。
    *   `callbacks`：它定义了训练期间要调用的回调列表。一个变量可以有一个或多个回调：`onTrainBegin()`、`onTrainEnd()`、`onEpochBegin()`、`onEpochEnd()`、`onBatchBegin()`、`onBatchEnd()`、`onYield()`。
    *   `validationData`：用于在最终模型之间进行选择时给出最终模型的估计值。这可以是以下任何一种：一个`[xVal, yVal]`数组，一个包含`{xs: xVal, ys: yVal}`形式元素的数据集对象。
    *   `validationBatchSize`：是一个定义批次大小的数字。它用于验证批次大小。这意味着我们不能一次性放入超过此值的所有数据集。其默认值为 32。
    *   `validationFreq`：用于验证样本批次。它用于在每个轮次结束时抽取验证数据进行验证。
    *   `classWeight`：用于对损失函数进行加权。它可能有助于告诉模型更多地关注来自样本不足的类的样本。
    *   `initialEpoch`：用于定义开始训练的轮数值。这对于恢复之前的训练非常有用。
    *   `yieldEvery`：它定义了将主线程让给其他任务的频率配置。它可以是`auto`，这意味着以特定的帧速率产生。`batch`，如果值是这个，它将每批产生一次。`epoch`，如果值是这个，它每轮产生一次。任何数字，如果值是任何数字，它每毫秒产生一次数字。`never`，如果值是这个，它将永远不会产生。

## 返回值

`Promise<History>`

## 示例 1

在本例中，我们将使用数组数据集训练模型。

### Javascript

```
import * as tf from "@tensorflow/tfjs"

// Creating model
const gfg_Model = tf.sequential() ;

// Adding layer to model
const config = {units: 1, inputShape: [2]}
const gfg_layer = tf.layers.dense(config);
gfg_Model.add(gfg_layer);

// Compiling the model
const config2 = {optimizer: 'sgd', loss: 'meanSquaredError'} 
gfg_Model.compile(config2);

// Creating Datasets for training
const array1 = [[1,2], [1,4], [1,3], [3,4]];
const array2 = [1, 1];
const arrData1 = tf.data.array(array1);
const arrData2 = tf.data.array(array2);

const config3 = {xs:arrData1, ys:arrData2}
const arrayDataset = tf.data.zip(config3)
const ArrayDataset = arrayDataset.batch(3).shuffle(6);

// Training the model
const Tm = await gfg_Model.fitDataset(ArrayDataset, { epochs: 3 });

// Printing the loss after training
console.log("Loss " + " : " + Tm.history.loss[0]);
```

### 输出

```
Loss : 0.428712397813797
```

## 示例 2

在本例中，我们将使用由 csv 文件制作的数据集来训练我们的模型。

### Javascript

```
import * as tf from "@tensorflow/tfjs";

// Path for the CSV file
const gfg_CsvFile =
  "https://storage.googleapis.com/tfjs-examples/multivariate-linear-regression/data/boston-housing-train.csv";

// Creating model
const gfg_Model = tf.sequential();

// Adding layer to model
const config = { units: 1, inputShape: [12] };
const gfg_layer = tf.layers.dense(config);
gfg_Model.add(gfg_layer);

// Compiling the model
const opt = tf.train.sgd(0.0001);
gfg_Model.compile({ optimizer: opt, loss: "meanSquaredError" });

// Here we want to predict column tax
const config2 = { columnConfigs: { tax: { isLabel: true } } };
const csvDataset = tf.data.csv(gfg_CsvFile, config2);

// Creating dataset for training
const flattenedDataset = csvDataset
  .map(({ xs, ys }) => {
    return { xs: Object.values(xs), ys: Object.values(ys) };
  })
  .batch(5);

// Training the model
const Tm = await gfg_Model.fitDataset(flattenedDataset, { epochs: 5 });

for (let i = 0; i < 5; i++) {
  console.log(Tm.history.loss[i]);
}
```

### 输出

```
21489.68359375
8750.29296875
6632.365234375
5908.6171875
5546.45654296875
```

## 参考

[https://js.tensorflow.org/api/latest/#tf.Sequential.fitDataset](https://js.tensorflow.org/api/latest/#tf.Sequential.fitDataset)