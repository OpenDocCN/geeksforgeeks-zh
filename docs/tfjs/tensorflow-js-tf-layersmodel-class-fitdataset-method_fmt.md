# TensorFlow.js tf.LayersModel 类的 fitDataset() 方法

> 原文: [https://www.geeksforgeeks.org/tensorflow-js-tf-layersmodel-class-fitdataset-method/](https://www.geeksforgeeks.org/tensorflow-js-tf-layersmodel-class-fitdataset-method/)

TensorFlow.js 是谷歌开发的开源库，用于在浏览器或 Node.js 环境中运行机器学习模型和深度学习神经网络。`tf.LayersModel` 类的 `fitDataset()` 方法用于通过使用数据集对象来训练层模型。

## 语法

```
layerModel.fitDataset(dataset, args);
```

## 参数

该方法接受以下参数：

*   `dataset`：输入值，形式为数据集，我们用它来训练层模型。
*   `args`：一个对象，包含以下值：
    *   `batchesPerEpoch`：每个 epoch 中的批次数量。它取决于批次大小。随着批次大小的增加，其大小也会减小。
    *   `epochs`：训练模型期间训练数据集中的总迭代次数。它应该是一个整数值。
    *   `initialEpoch`：用于定义开始训练的 epoch 值。
    *   `validationData`：用于在最终模型之间进行选择时给出最终模型的估计值。
    *   `verbose`：用于显示每个 epoch 的进度。如果值为 0，表示在 `fit()` 调用期间不打印任何消息。如果值为 1，在 Node.js 中，它将打印一个进度条。在浏览器中，它不显示任何操作。值 1 是默认值。值 2 尚未实现。
    *   `classWeight`：用于对损失函数进行加权。它可能有助于告诉模型更多地关注来自样本不足的类的样本。
    *   `callbacks`：定义训练期间要调用的回调列表。一个变量可以有一个或多个回调：`onTrainBegin()`、`onTrainEnd()`、`onEpochBegin()`、`onEpochEnd()`、`onBatchBegin()`、`onBatchEnd()`、`onYield()`。
    *   `validationBatchSize`：一个定义批次大小的数字。它用于验证批次大小。这意味着我们不能一次放入超过此值的所有数据集。其默认值为 32。
    *   `validationBatches`：用于验证样本批次。它用于在每个周期结束时抽取验证数据进行验证。
    *   `yieldEvery`：定义将主线程让给其他任务的频率配置。它可以是 `auto`，这意味着以特定的帧速率产生。`batch`，如果值是这个，它将产生每个批次。`epoch`，如果值是这个，它产生每个 epoch。任何数字，如果值是任何数字，它每毫秒产生一次数字。`never`，如果值是这个，它将永远不会产生。

## 返回值

`Promise<History>`

## 示例 1

在本例中，我们将使用 CSV 数据集训练我们的层模型。

### JavaScript

```javascript
import * as tf from "@tensorflow/tfjs"

// Path for the CSV file
const gfg_CsvFile =
'https://storage.googleapis.com/tfjs-examples/multivariate-linear-regression/data/boston-housing-train.csv';

async function run() {

// Creating model
    const gfg_LayerModel = tf.sequential();

// Adding layer to model
    const config = { units: 1, inputShape: [12] }
    const gfg_layer = tf.layers.dense(config);
    gfg_LayerModel.add(gfg_layer);

// Compiling the model
    const opt = tf.train.sgd(0.00000001)
    gfg_LayerModel.compile({ optimizer: opt,
            loss: 'meanSquaredError' });

// Here we want to predict column tax
    const config2 = { columnConfigs: {
             rad: { isLabel: true } } };

const csvDataset = tf.data.csv(gfg_CsvFile, config2);

// Creating dataset for training
    const flattenedDataset =
        csvDataset.map(({ xs, ys }) => {
            return { xs: Object.values(xs),
                    ys: Object.values(ys) };
        }).batch(6);

// Training the model
    const Tm = await gfg_LayerModel.fitDataset(
            flattenedDataset, { epochs: 10 });

for (let i = 0; i < 6; i++) {
        console.log(Tm.history.loss[i])
    }
}
run();
```

### 输出

```
41480.109375
28887.93359375
20162.228515625
14115.478515625
9924.9404296875
7020.56005859375
```

## 示例 2

在本例中，我们将使用数组的数据集训练我们的层模型。

### JavaScript

```javascript
import * as tf from "@tensorflow/tfjs"

async function run() {

// Creating Layer model
    const gfg_LayerModel = tf.sequential();

// Adding layer to model
    const config = { units: 4, inputShape: [4] }
    const gfg_layer = tf.layers.dense(config);
    gfg_LayerModel.add(gfg_layer);

// Compiling the model
    const config2 = { optimizer: 'sgd', loss: 'meanSquaredError' }
    gfg_LayerModel.compile(config2);

// Creating Datasets for training
    const array1 = [
        [1, 2, 3, 4],
        [1, 4, 6, 8],
        [1, 3, 4, 7],
        [3, 4, 7, 8]
    ];
    const array2 = [1, 1, 1, 1];
    const arrData1 = tf.data.array(array1);
    const arrData2 = tf.data.array(array2);

const config3 = { xs: arrData1, ys: arrData2 }
    const arrayDataset = tf.data.zip(config3)
    const ArrayDataset = arrayDataset.batch(4);

// Training the model
    const Tm = await gfg_LayerModel.fitDataset(
            ArrayDataset, { epochs: 4 });

// Printing the loss after training
    console.log("Loss After Training Layer Model"
        + Tm.history.loss[0]);
}
run();
```

### 输出

```
Loss After Training Layer Model 4.386415958404541
```

## 参考

[https://js.tensorflow.org/api/latest/#tf.LayersModel.fitDataset](https://js.tensorflow.org/api/latest/#tf.LayersModel.fitDataset)