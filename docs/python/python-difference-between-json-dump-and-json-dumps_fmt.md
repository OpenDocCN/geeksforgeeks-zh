# Python中json.dumps()与json.dump()的区别

> 原文：[https://www.geeksforgeeks.org/python-difference-between-json-dump-and-json-dumps/](https://www.geeksforgeeks.org/python-difference-between-json-dump-and-json-dumps/)

[JSON](https://www.geeksforgeeks.org/javascript-json/) 是一种轻量级的数据交换数据格式，人类可以轻松读写，机器可以轻松解析生成。这是一种完全独立于语言的文本格式。为了处理 json 数据，Python 有一个名为 `json` 的内置包。
**注：**更多信息，请参考[使用 Python 中的 JSON 数据](https://www.geeksforgeeks.org/working-with-json-data-in-python/)

## json.dumps()

`json.dumps()`方法可以将 Python 对象转换为 json 字符串。

> **语法：** `json.dumps(dict，indent)`
> **参数：**
> *   `dict` – 应该转换为 JSON 对象的字典的名称。
> *   `indent` – 定义缩进的单位数

**例：**

```py
# Python program to convert
# Python to JSON

import json

# Data to be written
dictionary ={
  "id": "04",
  "name": "sunil",
  "department": "HR"
}

# Serializing json 
json_object = json.dumps(dictionary, indent = 4)
print(json_object)
```

**输出：**

```py
{
    "department": "HR",
    "id": "04",
    "name": "sunil"
}
```

**Python 对象及其到 JSON 的等价转换：**

| Python类型 | 等效 JSON |
| --- | --- |
| dict | object |
| list，tuple | array |
| str | string |
| int，float | number |
| True | true |
| False | false |
| None | null |

## json.dump()

`json.dump()`方法可用于写入 json 文件。

> **语法：** `json.dump(dict，file_pointer)`
> **参数：**
> *   `dict` – 应该转换为 JSON 对象的字典的名称。
> *   `file_pointer` – 以写入或追加模式打开的文件的指针。

**例：**

```py
# Python program to write JSON
# to a file

import json

# Data to be written
dictionary ={
    "name" : "sathiyajith",
    "rollno" : 56,
    "cgpa" : 8.6,
    "phonenumber" : "9976770500"
}

with open("sample.json", "w") as outfile:
    json.dump(dictionary, outfile)
```

**输出：**

![python-json-write-to-file](img/3e48df55c216accfb8603777eecdf4d6.png)