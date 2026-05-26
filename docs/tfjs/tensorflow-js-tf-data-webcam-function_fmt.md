# TensorFlow.js tf.data.webcam()功能

> 原文：[https://www.geeksforgeeks.org/tensorflow-js-tf-data-webcam-function/](https://www.geeksforgeeks.org/tensorflow-js-tf-data-webcam-function/)

**TensorFlow.js** 是谷歌开发的开源库，用于在浏览器或节点环境下运行机器学习模型和深度学习神经网络。

`tf.data.webcam()` 函数用于创建迭代器，该迭代器从网络摄像头视频流中生成张量。

**注意：** 仅当设备包含网络摄像头时，才在浏览器环境下工作。

**语法：**

```
tf.data.webcam(webcamVideoElement?, webcamConfig?)
```

**参数：**

*   `webcamVideoElement`：用于播放网络摄像头视频的元素。
*   `webcamConfig`：一个对象，包含使用网络摄像头从视频流中操作和读取数据的配置。

**返回值：** 返回一个 Promise。

## 示例

```javascript
// 导入 tensorflow.js 库
import * as tf from "@tensorflow/tfjs"

// 返回摄像头的 Promise
let camera = await tf.data.webcam(document.createElement('video'));

// 返回图像捕获的 Promise
let image = await camera.capture();

// 打印结果
image.print();

// 停止摄像头
camera.stop();
```

## 输出

```
Tensor
    [[[168, 176, 185],
      [164, 171, 180],
      [161, 169, 178],
      ...,
      [43 , 91 , 74 ],
      [37 , 90 , 70 ],
      [41 , 94 , 74 ]],

[[165, 172, 181],
      [166, 174, 182],
      [164, 171, 180],
      ...,
      [45 , 93 , 77 ],
      [38 , 92 , 71 ],
      [41 , 94 , 74 ]],

[[152, 174, 178],
      [156, 178, 182],
      [158, 178, 182],
      ...,
      [60 , 89 , 79 ],
      [56 , 90 , 74 ],
      [55 , 89 , 73 ]],

...
     [[150, 174, 98 ],
      [147, 171, 95 ],
      [136, 168, 87 ],
      ...,
      [13 , 27 , 2  ],
      [21 , 29 , 8  ],
      [21 , 29 , 8  ]],

[[134, 170, 92 ],
      [138, 173, 96 ],
      [130, 169, 84 ],
      ...,
      [16 , 33 , 0  ],
      [22 , 33 , 7  ],
      [21 , 32 , 6  ]],

[[132, 167, 90 ],
      [130, 165, 88 ],
      [128, 167, 82 ],
      ...,
      [19 , 36 , 3  ],
      [24 , 35 , 9  ],
      [22 , 33 , 7  ]]]
```

**参考：** [https://js.tensorflow.org/api/latest/#data.webcam](https://js.tensorflow.org/api/latest/#data.webcam)