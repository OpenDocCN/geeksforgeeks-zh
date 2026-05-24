# 如何用 Python 将多个 Excel 文件合并成单个文件？

> 原文: [https://www.geeksforgeeks.org/how-to-merge-multiple-excel-files-into-a-single-files-with-python/](https://www.geeksforgeeks.org/how-to-merge-multiple-excel-files-into-a-single-files-with-python/)

通常，我们使用的是 Excel 文件，我们肯定遇到过需要将多个 Excel 文件合并成一个的情况。传统的方法一直是在 Excel 中使用 VBA 代码，这是一个多步骤的过程，不太容易理解。另一种方法是手动将长的 Excel 文件复制到一个文件中，这不仅耗时、麻烦，而且容易出错。

使用 `pandas` 模块在 Python 中只需几行代码就可以轻松快速地完成这项任务。首先，我们需要用 `pip` 安装模块。所以让我们把这个步骤移开。

在终端中使用以下命令:

```py
pip install pandas
```

## 方法 1: 使用 `DataFrame.append()`

`pandas` 的 `DataFrame.append()` 函数用于将其他数据帧的行追加到给定数据帧的末尾，返回一个新的数据帧对象。不在原始数据框中的列将作为新列添加，新单元格将填充 `NaN` 值。

> **语法:** `DataFrame.append(other, ignore_index=False, verify_integrity=False, sort=None)`
>
> **参数:**
>
> *   `other`: DataFrame 或 Series/dict 类对象，或这些对象的列表。
> *   `ignore_index`: 如果为 `True`，则不使用索引标签。默认值为 `False`。
> *   `verify_integrity`: 如果为 `True`，则在创建重复索引时会引发 `ValueError`。默认值为 `False`。
> *   `sort`: 如果列未对齐，则对列进行排序。默认值为 `False`。
>
> **返回:** 附加后的数据框

**示例:**

**使用的 Excel 文件:** [FoodSales1-1](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210525133803/FoodSales1-1.xlsx)、[FoodSales2-1](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210525133804/FoodSales2-1.xlsx)

```py
# importing the required modules
import glob
import pandas as pd

# specifying the path to csv files
path = "C:/downloads"

# csv files in the path
file_list = glob.glob(path + "/*.xlsx")

# list of excel files we want to merge.
# pd.read_excel(file_path) reads the excel
# data into pandas dataframe.
excl_list = []

for file in file_list:
    excl_list.append(pd.read_excel(file))

# create a new dataframe to store the
# merged excel file.
excl_merged = pd.DataFrame()

for excl_file in excl_list:

    # appends the data into the excl_merged
    # dataframe.
    excl_merged = excl_merged.append(
      excl_file, ignore_index=True)

# exports the dataframe into excel file with
# specified name.
excl_merged.to_excel('total_food_sales.xlsx', index=False)
```