# Python 中如何使用 Pickle 保存和加载变量？

> 原文：[https://www.geeksforgeeks.org/how-to-use-pickle-to-save-and-load-variables-in-python/](https://www.geeksforgeeks.org/how-to-use-pickle-to-save-and-load-variables-in-python/)

序列化是一种用于保存任何进程中对象状态的技术。我们可以稍后通过反序列化来使用这个状态，以继续这个过程。`Pickle` 是一个 Python 模块，它使序列化或保存变量以及在需要时加载变量变得容易。与 `JSON` 序列化不同，`Pickle` 将对象转换为二进制字符串。`JSON` 是文本特定的，但是 `Pickle` 是 Python 特定的，它可以序列化 `JSON` 无法序列化的自定义类。由于这一特性，它被大量用于训练机器学习模型。本文讨论了如何使用 `pickle` 在 Python 中保存和加载变量。

## 使用的功能

在 Python 中，`dumps()` 方法用于将变量保存到 pickle 文件中。

**语法：**

> `pickle.dumps(obj, protocol=None, *, fix_imports=True, buffer_callback=None)`

在 Python 中，`loads()` 用于从一个腌制文件中加载保存的数据。

**语法：**

> `pickle.loads(data, /, *, fix_imports=True, encoding='ASCII', errors='strict', buffers=None)`

## 保存变量

### 方法 1：传递变量

在 `dumps()` 方法中，我们可以传递变量，它将为我们返回相同的二进制字符串。然后，我们可以将其传输到其他 Python 模块或保存在数据库中。

**示例：**

```py
import pickle

# Create a variable
myvar = [{'This': 'is', 'Example': 1}, 'of',
         'serialisation', ['using', 'pickle']]

# Use dumps() to make it serialized
serialized = pickle.dumps(myvar)

print(serialized)
```

**输出：**

> b'\x80\x04\x95K\x00\x00\x00\x00\x00\x00\x00]\x94(}\x94(\x8c\x04This\x94\x8c\x02is\x94\x8c\x07Example\x94K\x01u\x8c\x02of\x94\x8c\rserialisation\x94]\x94(\x8c\x05using\x94\x8c\x06pickle\x94ee.'

### 方法 2：直接保存到文件

我们可以直接将变量保存在文件本身。

**示例：**

```py
import pickle

# Create a variable
myvar = [{'This': 'is', 'Example': 2}, 'of',
         'serialisation', ['using', 'pickle']]

# Open a file and use dump()
with open('file.pkl', 'wb') as file:
    # A new file will be created
    pickle.dump(myvar, file)
```

## 加载变量

### 方法 1

`loads()` 方法采用二进制字符串并返回相应的变量。如果字符串无效，它将抛出一个 `PickleError`。

**示例：**

```py
import pickle

# This is the result of previous code
binary_string = b'\x80\x04\x95K\x00\x00\x00\x00\x00\x00\x00]\x94(}\x94(\x8c\x04This\x94\x8c\x02is\x94\x8c\x07Example\x94K\x01u\x8c\x02of\x94\x8c\rserialisation\x94]\x94(\x8c\x05using\x94\x8c\x06pickle\x94ee.'

# Use loads to load the variable
myvar = pickle.loads(binary_string)

print(myvar)
```

**输出：**

> [{'This': 'is', 'Example': 1}, 'of', 'serialisation', ['using', 'pickle']]

### 方法 2

`load()` 方法加载一个腌制文件并返回一个反序列化的变量。

**示例：**

```py
import pickle

# Open the file in binary mode
with open('file.pkl', 'rb') as file:
    # Call load method to deserialize
    myvar = pickle.load(file)
    print(myvar)
```

**输出：**

> [{'This': 'is', 'Example': 2}, 'of', 'serialisation', ['using', 'pickle']]