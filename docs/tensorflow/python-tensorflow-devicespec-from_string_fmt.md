# TensorFlow: DeviceSpec.from_string()

> 原文: [https://www.geeksforgeeks.org/python-tensorflow-devicespec-from_string/](https://www.geeksforgeeks.org/python-tensorflow-devicespec-from_string/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

`from_string` 用于从字符串生成 `DeviceSpec`。

> **语法:** `tf.DeviceSpec.from_string(spec)`
>
> **参数:**
>
> *   `spec`: 是格式为 `/job:<name>/replica:<id>/task:<id>/device:CPU:<id>` 或 `/job:<name>/replica:<id>/task:<id>/device:GPU:<id>` 的字符串，所有条目都是可选的。
>
> **返回:** 返回字符串生成的 `DeviceSpec` 对象。

## 示例 1

```py
# Importing the library
import tensorflow as tf

# Formatting the string
spec = '/job:gfg / replica:1 / task:2'

# Initializing Device Specification
device_spec = tf.DeviceSpec.from_string(spec)

# Printing the DeviceSpec object
print('Device Spec: ', device_spec)
```

**输出:**

```py
Device Spec:  <tensorflow.python.framework.device_spec.DeviceSpecV2 object at 0x7fadb9428168>
```

## 示例 2

```py
# Importing the library
import tensorflow as tf

# Formatting the string
spec = '/job:gfg / replica:2 / task:3'

# Initializing Device Specification
device_spec = tf.DeviceSpec.from_string(spec)

# Printing the DeviceSpec object
print('Device Spec: ', device_spec)
```

**输出:**

```py
Device Spec:  <tensorflow.python.framework.device_spec.DeviceSpecV2 object at 0x7fadb9428228>
```