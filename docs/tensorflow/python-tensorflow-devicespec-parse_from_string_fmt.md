# TensorFlow: DeviceSpec.parse_from_string()

> 原文: [https://www.geeksforgeeks.org/python-tensorflow-devicespec-parse_from_string/](https://www.geeksforgeeks.org/python-tensorflow-devicespec-parse_from_string/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

`parse_from_string()` 用于将设备规格名称解析为其组件。

## 语法

`tf.DeviceSpec.parse_from_string(spec)`

## 参数

*   `spec`: 是格式为 `/job:/replica:/task:/device:CPU:` 或 `/job:/replica:/task:/device:GPU` 的字符串，所有字段都是可选的。

## 返回

返回一个 `DeviceSpec` 对象。

## 示例

### 例 1

```py
# Importing the library
import tensorflow as tf

# Initializing Device Specification
device_spec = tf.DeviceSpec(job ="gfg", replica = 5)

# Printing the DeviceSpec 
print('Device Spec: ', device_spec.to_string())

# Getting new DeviceSpec object
new_device_spec = device_spec.parse_from_string("/GPU:0")

# Printing the result
print('New Device Spec: ', new_device_spec.to_string())
```

**输出:**

```py
Device Spec:  /job:gfg/replica:5
New Device Spec:  /device:GPU:0
```

### 例 2

```py
# Importing the library
import tensorflow as tf

# Initializing Device Specification
device_spec = tf.DeviceSpec(job ="gfg", replica = 5)

# Printing the DeviceSpec 
print('Device Spec: ', device_spec.to_string())

# Getting new DeviceSpec object
new_device_spec = device_spec.parse_from_string("replica:2 / GPU:0")

# Printing the result
print('New Device Spec: ', new_device_spec.to_string())
```

**输出:**

```py
Device Spec:  /job:gfg/replica:5
New Device Spec:  /replica:2/device:GPU:0
```