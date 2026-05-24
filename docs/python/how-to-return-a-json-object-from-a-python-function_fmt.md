# 如何从Python函数返回JSON对象？

> 原文：[https://www.geeksforgeeks.org/how-to-return-a-json-object-from-a-python-function/](https://www.geeksforgeeks.org/how-to-return-a-json-object-from-a-python-function/)

[JSON](https://www.geeksforgeeks.org/working-with-json-data-in-python/)的全形式是JavaScript对象符号。这意味着由编程语言中的文本组成的脚本（可执行）文件用于存储和传输数据。Python通过一个名为`json`的内置包支持JSON，这个模块可以用来将Python字典转换成JSON对象。在Python中字典是用来获取它的等价JSON对象的。

## 进场：

*   导入模块
*   创建函数
*   创建词典
*   使用 [`dumps()`](https://www.geeksforgeeks.org/json-dumps-in-python/) 方法将字典转换为JSON对象
*   返回JSON对象

> **语法：** `json.dumps(obj, *skipkeys=False, ensure_ascii=True, check_circular=True, allow_nan=True, cls=None, indent=None, separators=None, default=None, sort_keys=False, **kw)`

下面给出了使用上述方法的实现：

## 例 1：

```python
# Import Module
import json

# Create geeks function
def geeks():
    # Define Variable
    language = "Python"
    company = "GeeksForGeeks"
    Itemid = 1
    price = 0.00

    # Create Dictionary
    value = {
        "language": language,
        "company": company,
        "Itemid": Itemid,
        "price": price
    }

    # Dictionary to JSON Object using dumps() method
    # Return JSON Object
    return json.dumps(value)

# Call Function and Print it.
print(geeks())
```

**输出：**

> `{"language":"Python","company":"GeeksForGeeks","Itemid":1,"price":0.0}`

## 示例 2：使用列表作为字典值。

```python
# Import Module
import json

# Create geeks function
def geeks():
    # Create Dictionary
    value = {
        "firstName": "Pawan",
        "lastName": "Gupta",
        "hobbies": ["playing", "problem solving", "coding"],
        "age": 20,
        "children": [
            {
                "firstName": "mohan",
                "lastName": "bansal",
                "age": 15
            },
            {
                "firstName": "prerna",
                "lastName": "Doe",
                "age": 18
            }
        ]
    }

    # Dictionary to JSON Object using dumps() method
    # Return JSON Object
    return json.dumps(value)

# Call Function and Print it.
print(geeks())
```

**输出：**

> `{"firstName":"Pawan","lastName":"Gupta","hobbies":["playing","problem solving","coding"],"age":20,"children":[{"firstName":"mohan","lastName":"bansal","age":15},{"firstName":"prerna","lastName":"Doe","age":18}]}`