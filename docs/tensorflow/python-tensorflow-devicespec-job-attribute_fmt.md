# Python - TensorFlow DeviceSpec.job 属性

> 原文: [https://www.geeksforgeeks.org/python-tensorflow-devicespec-job-attribute/](https://www.geeksforgeeks.org/python-tensorflow-devicespec-job-attribute/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

`job` 属性用于从设备规格中获取作业名称。

> **语法:** `tf.DeviceSpec.job`
>
> **返回:** 返回设备规格的作业名称。

## 示例 1

```py
# Importing the library
import tensorflow as tf

# Initializing Device Specification
device_spec = tf.DeviceSpec(job ="gfg", device_type ="GPU", device_index = 1)

# Printing the DeviceSpec object
print('Device Spec: ', device_spec)

# Getting the job
job = device_spec.job

# Printing the result
print('Job: ', job)
```

**输出:**

```py
Device Spec:  <tensorflow.python.framework.device_spec.DeviceSpecV2 object at 0x7fe5ba9810a8>
Job:  gfg
```

## 示例 2

```py
# Importing the library
import tensorflow as tf

# Initializing Device Specification
device_spec = tf.DeviceSpec(job ="gfg2", device_type ="GPU", device_index = 1)

# Printing the DeviceSpec object
print('Device Spec: ', device_spec)

# Getting the job
job = device_spec.job

# Printing the result
print('Job: ', job)
```

**输出:**

```py
Device Spec:  <tensorflow.python.framework.device_spec.DeviceSpecV2 object at 0x7fe5ba981108>
Job:  gfg2
```