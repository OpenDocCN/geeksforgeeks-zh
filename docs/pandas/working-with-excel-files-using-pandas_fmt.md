# 使用熊猫处理 Excel 文件

> 原文：[https://www.geeksforgeeks.org/working-with-excel-files-using-pandas/](https://www.geeksforgeeks.org/working-with-excel-files-using-pandas/)

Excel 工作表是信息技术行业中最常见的文件形式之一。每个曾经使用过电脑的人都曾接触过 Excel 电子表格。Excel 之所以如此受欢迎，是因为它在表格和系统形式的数据存储和操作领域有着广泛的应用。此外，Excel 工作表是非常本能和用户友好的，这使得它非常适合操作大型数据集，即使对于技术水平较低的人来说。如果你正在寻找学习使用 Python 操作和自动化 Excel 文件的地方，那就不要再找了。你来对地方了。

在本文中，您将学习如何使用 Pandas 来处理 Excel 电子表格。在文章的最后，您将了解：

*   这需要必要的模块以及如何在您的系统中设置它们。
*   用 Python 将 Excel 文件中的数据读入 Pandas。
*   探索 Pandas Excel 文件中的数据。
*   使用函数操作和重塑 Pandas 中的数据。

## 安装

要在 Anaconda 中安装 Pandas，我们可以在 Anaconda 终端中使用以下命令：

```py
conda install pandas
```

要在普通 Python（非 Anaconda）中安装 Pandas，我们可以在命令提示符下使用以下命令：

```py
pip install pandas
```

## 入门指南

### 导入模块

首先，我们需要导入 pandas 模块，这可以通过运行以下命令来完成：

```py
import pandas as pds
```

### 读取 Excel 文件

**输入文件：** 假设 Excel 文件是这样的

**表 1：**
![python-pandas](img/e05d3a77bc60abe389fbb61752f91f9f.png)

**第 2 页：**
![python-pandas-read-excel](img/d0efdfa2d4a5255caab1f1271354b983.png)

现在我们可以在 pandas 中使用 `read_excel` 函数导入 Excel 文件，如下图所示：

```py
file = ('path_of_excel_file')
newData = pds.read_excel(file)
newData
```

**输出：**
![python-pandas-read-excel](img/f56b1a56a24140f05206d5ca507ee79d.png)

第二条语句从 Excel 中读取数据，并将其存储到 Pandas 数据框中，Pandas 数据框由变量 `newData` 表示。如果 Excel 工作簿中有多张工作表，该命令将导入第一张工作表的数据。要制作包含工作簿中所有工作表的数据框，最简单的方法是分别创建不同的数据框，然后将它们连接起来。`read_excel` 方法采用参数 `sheet_name` 和 `index_col`，在这两个参数中，我们可以指定数据框应该由哪张纸组成，`index_col` 指定标题列。

**示例：**

```py
sheet1 = pds.read_excel(file,
                        sheet_name = 0,
                        index_col = 0)

sheet2 = pds.read_excel(file,
                        sheet_name = 1,
                        index_col = 0)

newData = pds.concat([sheet1, sheet2])
```

第三条语句将两个工作表连接起来。现在要检查整个数据帧，我们可以简单地运行以下命令：

```py
newData
```

**输出：**
![python-pandas-read-excel](img/05d298d94684d5903774a86358563a10.png)

### 查看数据

要从数据框的顶部和底部查看 5 列，我们可以运行以下命令：

```py
newData.head()
newData.tail()
```

**输出：**
![python-pandas-read-excel](img/f24812820504f934737e1908059a3dbe.png)
![python-pandas-read-excel](img/6b6e53c145e241e892ad10e359f167f9.png)

`head()` 和 `tail()` 方法也把参数作为要显示的列数的数字。

### 获取数据形状

可以使用 `shape` 属性查看数据框中的行数和列数，如下所示：

```py
newData.shape
```

**输出：**
![python-pandas-read-excel](img/f2dd68702326d0fc3e87b6c915116395.png)

### 排序数据

如果任何列包含数字数据，我们可以使用 Pandas 中的 `sort_values()` 方法对该列进行排序，如下所示：

```py
sorted_column = newData.sort_values(['Height'], ascending = False)
```

现在，假设我们想要排序列的前 5 个值，我们可以在这里使用 `head()` 方法：

```py
sorted_column['Height'].head(5)
```

**输出：**
![python-pandas-read-excel](img/d65c8ac1b8ce9c5b6e0a315a678fad34.png)

我们可以通过数据框的任意数字列来实现，如下所示：

```py
newData['Weight'].head()
```

**输出：**
![python-pandas-read-excel](img/7152401ff93e418cf1a2c18179b7f972.png)

### 获取统计信息

现在，假设我们的数据大部分是数字。我们可以得到平均值、最大值、最小值等统计信息。关于数据框使用 `describe()` 方法如下所示：

```py
newData.describe()
```

**输出：**
![python-pandas-read-excel](img/553b8510ebddf3c8511e58269c2234e4.png)

也可以使用以下命令对所有数值列分别执行此操作：

```py
newData['Weight'].mean()
```

**输出：**
![python-pandas-read-excel](img/60d567e95197eedca68296a57b04ea4d.png)

也可以使用相应的方法计算其他统计信息。

### 创建计算列

和 Excel 一样，公式也可以应用，计算列可以如下创建：

```py
newData['calculated_column'] = newData["Height"] + newData["Weight"]
newData['calculated_column'].head()
```

**输出：**
![python-pandas-read-excel](img/04cc136afc4e6c406d07a7c98f41fcaa.png)

### 导出数据

对数据框中的数据进行操作后，我们可以使用 `to_excel` 方法将数据导出回 Excel 文件。为此，我们需要指定一个输出 Excel 文件来写入转换后的数据，如下所示：

```py
newData.to_excel('Output File.xlsx')
```

**输出：**
![python-pandas-read-excel](img/103f0be3f5d862330a45909a3564921f.png)