# 在 Python 中展平 JSON 对象

> 原文：[https://www.geeksforgeeks.org/flattening-json-objects-in-python/](https://www.geeksforgeeks.org/flattening-json-objects-in-python/)

[JSON](https://www.geeksforgeeks.org/javascript-json/)（JavaScript 对象符号）是一种人类可读文本的数据交换格式，用于传输数据，尤其是在网络应用程序和服务器之间。JSON 文件就像 Python 中的嵌套字典。要将一个文本文件转换成 JSON，Python 中有一个 `json` 模块。该模块内置 Python 标准模块，无需外接安装。

扁平化 JSON 什么都不是，但是不存在嵌套，只存在键值对。

**示例：**

> **未扁平化的 JSON：**
> ```json
> {
>   "user": {
>     "Rachel": {
>       "UserID": 1717171717,
>       "Email": "Rachel1999@gmail.com",
>       "friends": ["John", "Jeremy", "Emily"]
>     }
>   }
> }
> ```
>
> **扁平化 JSON：**
> ```json
> {
>   "user_Rachel_friends_2": "Emily",
>   "user_Rachel_friends_0": "John",
>   "user_Rachel_UserID": 1717171717,
>   "user_Rachel_Email": "Rachel1999@gmail.com",
>   "user_Rachel_friends_1": "Jeremy"
> }
> ```

## 需要扁平化 JSON

需要展平 JSON 的原因有很多，比如为了一个更好、更容易理解的视图，即只存在键值对，没有任何嵌套。它还允许以可读但更详细的方式实现特定于上下文的安全性和约束。

## 一种扁平化 JSON 的方法

有很多方法可以展平 JSON。使用 `json-flatten` 库有一种递归方式和另一种递归方式。

### 递归方法

现在我们可以通过递归方法来展平字典数组，这种方法很容易理解。递归方法比使用 `json-flatten` 库稍慢一些。

**示例：**

```python
# for a array value of a key
unflat_json = {'user' :
               {'Rachel':
                {'UserID':1717171717,
                'Email': 'rachel1999@gmail.com',
                'friends': ['John', 'Jeremy', 'Emily']
                }
               }
              }

# Function for flattening json
def flatten_json(y):
    out = {}

    def flatten(x, name =''):
        # If the Nested key-value pair is of dict type
        if type(x) is dict:
            for a in x:
                flatten(x[a], name + a + '_')

        # If the Nested key-value pair is of list type
        elif type(x) is list:
            i = 0
            for a in x:
                flatten(a, name + str(i) + '_')
                i += 1
        else:
            out[name[:-1]] = x

    flatten(y)
    return out

# Driver code
print(flatten_json(unflat_json))
```

**输出：**

> ```json
> {
>   "user_Rachel_friends_2": "Emily",
>   "user_Rachel_friends_0": "John",
>   "user_Rachel_UserID": 1717171717,
>   "user_Rachel_Email": "Rachel1999@gmail.com",
>   "user_Rachel_friends_1": "Jeremy"
> }
> ```

### 使用 `flatten_json` 库

`json-flatten` 库提供了将 JSON 对象展平为单个键值对，以及将该字典反扁平化回 JSON 对象的函数。

#### 安装库

为了使用 `flatten_json` 库，我们需要安装这个库。可以通过在终端中运行以下命令来安装 `flatten_json`。

```bash
pip install json-flatten
```

**示例：**

```python
from flatten_json import flatten

unflat_json = {'user' :
               {'Rachel':
                {'UserID':1717171717,
                'Email': 'rachel1999@gmail.com',
                'friends': ['John', 'Jeremy', 'Emily']
                }
               }
              }

flat_json = flatten(unflat_json)

print(flat_json)
```

**输出：**

> ```json
> {
>   "user_Rachel_UserID": 1717171717,
>   "user_Rachel_Email": "Rachel1999@gmail.com",
>   "user_Rachel_friends_0": "John",
>   "user_Rachel_friends_1": "Jeremy",
>   "user_Rachel_friends_2": "Emily"
> }
> ```