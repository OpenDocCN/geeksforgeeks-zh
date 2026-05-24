# 如何将Python字典保存到CSV文件中？

> 原文：[https://www.geeksforgeeks.org/how-to-save-a-python-dictionary-to-a-csv-file/](https://www.geeksforgeeks.org/how-to-save-a-python-dictionary-to-a-csv-file/)

## 先决条件
[使用Python中的csv文件](https://www.geeksforgeeks.org/working-csv-files-python/)

## CSV文件介绍
**CSV（逗号分隔值）**文件是以字符串形式传输数据的最简单方法之一，尤其是传输到任何电子表格程序，如微软Excel或谷歌电子表格。在本文中，我们将看到如何将Python字典保存到CSV文件中。按照以下步骤进行操作。

### 1. 导入csv模块
```py
import csv
```

### 2. 创建域名列表
```py
field_names= ['No', 'Company', 'Car Model']
```

### 3. 创建Python字典列表
```py
cars = [
    {"No":1, "Company":"Ferrari", "Car Model":"488 GTB"},
    {"No":2, "Company":"Porsche", "Car Model":"918 Spyder"},
    {"No":3, "Company":"Bugatti", "Car Model":"La Voiture Noire"},
    {"No":4, "Company":"Rolls Royce", "Car Model":"Phantom"},
    {"No":5, "Company":"BMW", "Car Model":"BMW X7"},
]
```

### 4. 将字典内容写入CSV文件
```py
with open('Names.csv', 'w') as csvfile:
    writer = csv.DictWriter(csvfile, fieldnames=field_names)
    writer.writeheader()
    writer.writerows(cars)
```

## 语法
```py
DictWriter( (filename), fieldnames = [list of field names] )
```

在上面的代码片段中，`writer`是`csv`的一个`DictWriter`类实例，并使用以下两种方法：
1.  `DictWriter.writeheader()`用于将一行列标题/字段名称写入给定的CSV文件。
2.  `csvwriter.writerows()`方法用于将数据行写入指定文件。

**注意：**要在CSV文件中编写单个字典，请使用`writerow()`方法。

## 完整代码
```py
import csv

field_names = ['No', 'Company', 'Car Model']

cars = [
    {'No': 1, 'Company': 'Ferrari', 'Car Model': '488 GTB'},
    {'No': 2, 'Company': 'Porsche', 'Car Model': '918 Spyder'},
    {'No': 3, 'Company': 'Bugatti', 'Car Model': 'La Voiture Noire'},
    {'No': 4, 'Company': 'Rolls Royce', 'Car Model': 'Phantom'},
    {'No': 5, 'Company': 'BMW', 'Car Model': 'BMW X7'},
    ]

with open('Names.csv', 'w') as csvfile:
    writer = csv.DictWriter(csvfile, fieldnames = field_names)
    writer.writeheader()
    writer.writerows(cars)
```

## 输出
![python-dictionary-to-csv](img/7903d4154f2007cb4f573b7eb3952b28.png)