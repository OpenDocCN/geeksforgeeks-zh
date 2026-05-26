# DataFrame.to_pickle()

> 原文: [https://www.geeksforgeeks.org/dataframe-to_pickle-in-function-pandas/](https://www.geeksforgeeks.org/dataframe-to_pickle-in-function-pandas/)

`to_pickle()` 方法用于将给定对象序列化（pickle）到文件中。此方法使用下面给出的语法：

**语法：**

```py
DataFrame.to_pickle(self, path,
                    compression='infer',
                    protocol=4)
```

<figure class="table">

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| `path` | `str` | 存储序列化对象的文件路径。 |
| `compression` | `{'infer', 'gzip', 'bz2', 'zip', 'xz', None}` | 一个字符串，表示要在输出文件中使用的压缩。默认情况下，从指定路径中的文件扩展名推断。 |
| `protocol` | `int` | Int，表示 pickler 应该使用哪种协议，默认为最高协议（见[1]_ 第 12.1.2 段）。可能的值是 0、1、2、3、4。`protocol` 参数的负值相当于将其值设置为最高协议。 |

</figure>

### 示例 1

```py
# importing packages
import pandas as pd

# dictionary of data
dct = {'ID': {0: 23, 1: 43, 2: 12,
              3: 13, 4: 67, 5: 89,
              6: 90, 7: 56, 8: 34}, 
       'Name': {0: 'Ram', 1: 'Deep',
                2: 'Yash', 3: 'Aman', 
                4: 'Arjun', 5: 'Aditya',
                6: 'Divya', 7: 'Chalsea',
                8: 'Akash' }, 
       'Marks': {0: 89, 1: 97, 2: 45, 3: 78,
                 4: 56, 5: 76, 6: 100, 7: 87,
                 8: 81}, 
       'Grade': {0: 'B', 1: 'A', 2: 'F', 3: 'C',
                 4: 'E', 5: 'C', 6: 'A', 7: 'B',
                 8: 'B'}
      }

# forming dataframe and printing
data = pd.DataFrame(dct)
print(data)

# using to_pickle function to form file 
# with name 'pickle_file'
data.to_pickle('pickle_file')
```

**输出：**

```py
   ID     Name  Marks Grade
0  23      Ram     89     B
1  43     Deep     97     A
2  12     Yash     45     F
3  13     Aman     78     C
4  67    Arjun     56     E
5  89   Aditya     76     C
6  90    Divya    100     A
7  56  Chalsea     87     B
8  34    Akash     81     B
```

### 示例 2

```py
# importing packages
import pandas as pd

# dictionary of data
dct = {"f1": range(6), "b1": range(6, 12)}

# forming dataframe and printing
data = pd.DataFrame(dct)
print(data)

# using to_pickle function to form 
# file with name 'pickle_file'
data.to_pickle('pickle_file')
```

**输出：**

```py
   f1  b1
0   0   6
1   1   7
2   2   8
3   3   9
4   4  10
5   5  11
```