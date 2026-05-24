# Python：从给定的表达式列表中生成个性化数据

> 原文：[https://www.geeksforgeeks.org/python-generate-personalized-data-from-given-list-of-expressions/](https://www.geeksforgeeks.org/python-generate-personalized-data-from-given-list-of-expressions/)

## 问题描述

给定不同的表达式列表，任务是在 CSV 文件中为某些目的生成这些表达式的随机组合，例如测试数据库。这与序数数据模拟器相反，序数数据模拟器从随机数和标准名称生成数据集。

## 示例

**输入：** 自定义表达式列表
`Names = ['David', 'Emilia', 'John', 'Karmen']`
`Hobbies = ['Hiking', 'football', 'Gaming', 'Skydiving']`
`skills = ['Communication', 'leadership', 'cooking']`

**输出：** 一个包含表达式随机组合的 CSV 文件
```
Names, Age, Hobbies, skills
Emilia, 54, "['football', 'Hiking']", leadership
David, 22, "['Skydiving', 'Gaming']", cooking
Emilia, 59, "['football', 'Skydiving']", leadership
Emilia, 45, "['Gaming', 'football']", leadership
David, 62, "['Hiking', 'football']", cooking
David, 56, "['football', 'Hiking']", leadership
John, 17, "['Gaming', 'football']", cooking
David, 28, "['Gaming', 'football']", leadership
David, 28, "['Skydiving', 'football']", cooking
John, 17, "['Gaming', 'Skydiving']", cooking
John, 61, "['Hiking', 'football']", cooking
John, 44, "['Hiking', 'Gaming']", leadership
Emilia, 17, "['Hiking', 'Gaming']", Communication
Karmen, 34, "['football', 'Skydiving']", leadership
Emilia, 65, "['football', 'Hiking']", leadership
```

## 代码实现

```py
# importing libraries
import csv
import random

# create a csv file named "abc" that contains our dataset
with open('abc.csv', 'w', newline ='') as f: 
    file = csv.writer(f)
    file.writerow(['Names', 'Age', 'Hobbies', 'skills'])

# generate rows as much as wanted
    for i in range (1, 10) :                                   
        Names =['David', 'Emilia', 'John', 'Karmen']
        Hobbies =['Hiking', 'football', 'Gaming', 'Skydiving']
        skills =['Communication', 'leadership', 'cooking']
        file.writerow([random.choice(Names), random.randint(17, 65), 
                       random.sample(Hobbies, 2), random.choice(skills)])
```