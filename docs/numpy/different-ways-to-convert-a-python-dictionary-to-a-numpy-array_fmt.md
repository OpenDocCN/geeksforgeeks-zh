# 将 Python 字典转换为 NumPy 数组的不同方法

> 原文：[https://www.geeksforgeeks.org/different-ways-to-convert-a-python-dictionary-to-a-numpy-array/](https://www.geeksforgeeks.org/different-ways-to-convert-a-python-dictionary-to-a-numpy-array/)

在本文中，我们将看到使用 NumPy 库将 Python 字典转换为 NumPy 数组的不同方法。有时需要将 Python 中的[字典](https://www.geeksforgeeks.org/python-dictionary/)转换成 NumPy 数组，Python 提供了一种有效的方法来执行这个操作。将字典转换为 NumPy 数组会产生一个保存字典键值对的数组。

让我们看看不同的方法：

## 方法 1：使用 `numpy.array()` 和列表推导式

> **语法：** `numpy.array(*object*, *dtype=None*, ***, *copy=True*, *order='K'*, *subok=False*, *ndmin=0*)`
>
> **返回：** 满足指定要求的数组对象。

我们已经使用 `np.array()` 将字典转换为 nd 数组。为了将字典的每个值作为输入到 `np.array()` 的列表，使用了**列表推导式**的概念。

**示例：**

```py
# importing required librariess
import numpy as np
from ast import literal_eval

# creating class of string
name_list = """{
   "column0": {"First_Name": "Akash",
   "Second_Name": "kumar", "Interest": "Coding"},

"column1": {"First_Name": "Ayush",
   "Second_Name": "Sharma", "Interest": "Cricket"},

"column2": {"First_Name": "Diksha",
   "Second_Name": "Sharma","Interest": "Reading"},

"column3": {"First_Name":" Priyanka",
   "Second_Name": "Kumari", "Interest": "Dancing"}

}"""
print("Type of name_list created:\n",
      type(name_list))

# converting string type to dictionary
t = literal_eval(name_list)

# printing the original dictionary
print("\nPrinting the original Name_list dictionary:\n",
      t)

print("Type of original dictionary:\n",
      type(t))

# converting dictionary to numpy array
result_nparra = np.array([[v[j] for j in ['First_Name', 'Second_Name',
                                          'Interest']] for k, v in t.items()])

print("\nConverted ndarray from the Original dictionary:\n",
      result_nparra)

# printing the type of converted array
print("Type:\n", type(result_nparra))
```

**输出：**

> 创建的名称列表类型：
> `<class 'str'>`
>
> 正在打印原始 Name_list 字典：
> `{"column0": {"First_Name": "Akash", "Second_Name": "kumar", "Interest": "Coding"}, "column1": {"First_Name": "Ayush", "Second_Name": "Sharma", "Interest": "Cricket"}, "column2": {"First_Name": "Diksha", "Second_Name": "Sharma", "Interest": "Reading"}, "column3": {"First_Name": " Priyanka", "Second_Name": "Kumari", "Interest": "Dancing"}}`
>
> 从原始字典转换而来的数组：
> `[['Akash' 'kumar' 'Coding']`
>  `['Ayush' 'Sharma' 'Cricket']`
>  `['Diksha' 'Sharma' 'Reading']`
>  `[' Priyanka' 'Kumari' 'Dancing']]`
> 类型：
> `<class 'numpy.ndarray'>`

## 方法 2：使用 `numpy.array()` 和 `dictionary_obj.items()`

我们已经使用 `np.array()` 将字典转换为 nd 数组。为了获得字典的每个值作为 `np.array()` 方法的输入列表，使用了 `dictionary_obj.items()`。

**示例：**

```py
# importing library
import numpy as np

# creating dictionary as key as
# a number and value as its cube
dict_created = {0: 0, 1: 1, 2: 8, 3: 27,
                4: 64, 5: 125, 6: 216}

# printing type of dictionary created
print(type(dict_created))

# converting dictionary to
# numpy array
res_array = np.array(list(dict_created.items()))

# printing the converted array
print(res_array)

# printing type of converted array
print(type(res_array))
```

**输出：**

```py
<class 'dict'>
[[  0   0]
 [  1   1]
 [  2   8]
 [  3  27]
 [  4  64]
 [  5 125]
 [  6 216]]
<class 'numpy.ndarray'>
```