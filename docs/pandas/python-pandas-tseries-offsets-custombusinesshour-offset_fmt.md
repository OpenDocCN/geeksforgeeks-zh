# Python Pandas tseries.offsets.CustomBusinessHour.offset

> 原文：[https://www.geeksforgeeks.org/python-pandas-tseries-offsets-custombusinesshour-offset/](https://www.geeksforgeeks.org/python-pandas-tseries-offsets-custombusinesshour-offset/)

日期偏移量是 Pandas 中用于日期范围的一种标准的日期增量。就我们传递的关键字参数而言，它的工作原理与 `relativedelta` 完全一样。日期偏移的工作方式如下，每个偏移指定一组符合日期偏移的日期。例如，`Bday` 将该集合定义为工作日（M-F）的日期集合。

可以创建日期偏移量来将日期向前移动给定的有效日期数。例如，可以将 `Bday(2)` 添加到日期中，使其提前两个工作日。如果日期没有在有效日期开始，则首先将其移动到有效日期，然后创建偏移。

Pandas `tseries.offsets.CustomBusinessHour.offset` 属性返回一个 `datetime.timedelta` 值。这是 `self._offset` 的别名。

> **语法：** `pandas.tseries.offsets.CustomBusinessHour.offset`
>
> **参数：** 无
>
> **返回：** `datetime.timedelta`

## 示例 1

使用 `pandas.tseries.offsets.CustomBusinessHour.offset` 属性打印给定偏移量的 `self._offset` 偏移量值。

```py
# importing pandas as pd
import pandas as pd

# Creating Timestamp
ts = pd.Timestamp('2019-4-23 11:15:00')

# Create an offset
cbh = pd.tseries.offsets.CustomBusinessHour(n = 2, weekmask = 'Mon Tue Wed Thu',
                                           start ='12:00')

# Print the Timestamp
print(ts)

# Print the Offset
print(cbh)
```

**输出：**

![](img/e0dfb84ec590773846b3cb253771ae92.png)

![](img/4a18519f44fcbd1022ab3d34ee6834a3.png)

现在，我们将向给定的时间戳对象添加偏移量，以增加日期时间值。我们也会打印 `self._offset` 值。

```py
# Adding the offset to the given timestamp
new_timestamp = ts + cbh

# Print the updated timestamp
print(new_timestamp)

# return the self._offset value
result = cbh.offset

# print the result
print(result)
```

**输出：**

![](img/a30fa80851ee6ae90dbb5c876ec32328.png)

![](img/b6e4ffc93983547052aaac4afd0c76a2.png)

正如我们在输出中看到的，我们已经成功地创建了一个偏移量，并将其添加到给定的时间戳中。我们也打印了给定偏移量的 `self._offset` 值。

## 示例 2

使用 `pandas.tseries.offsets.CustomBusinessHour.offset` 属性打印给定偏移量的 `self._offset` 偏移量值。

```py
# importing pandas as pd
import pandas as pd

# Creating Timestamp
ts = pd.Timestamp('2019-4-23 11:15:00')

# Create an offset
cbh = pd.tseries.offsets.CustomBusinessHour(start ='07:00', end ='14:00')

# Print the Timestamp
print(ts)

# Print the Offset
print(cbh)
```

**输出：**

![](img/e0dfb84ec590773846b3cb253771ae92.png)

![](img/32e224c371cc0f205d6d43ed7ea7995b.png)

现在，我们将向给定的时间戳对象添加偏移量，以增加日期时间值。我们也会打印 `self._offset` 值。

```py
# Adding the offset to the given timestamp
new_timestamp = ts + cbh

# Print the updated timestamp
print(new_timestamp)

# move the passed timestamp to the
# return the self._offset value
result = cbh.offset

# print the result
print(result)
```

**输出：**

![](img/df360b6011955f9fe78ba406d14502d2.png)

![](img/b6e4ffc93983547052aaac4afd0c76a2.png)

正如我们在输出中看到的，我们已经成功地创建了一个偏移量，并将其添加到给定的时间戳中。我们也打印了给定偏移量的 `self._offset` 值。