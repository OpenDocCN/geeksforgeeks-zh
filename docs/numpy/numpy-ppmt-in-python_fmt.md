# Python 中的 `numpy.ppmt()`

> 原文: [https://www.geeksforgeeks.org/numpy-ppmt-in-python/](https://www.geeksforgeeks.org/numpy-ppmt-in-python/)

## 函数定义

`numpy.ppmt(rate, nper, pv, fv, when='end')`：该金融功能帮助用户只根据本金价值计算支付价值。

## 参数

> **`rate`**: 【标量或 (M, 数组)】每期十进制（非百分比）利率
> **`nper`**: 【标量或 (M, 数组)】总复合期
> **`fv`**: 【标量或 (M, 数组)】未来值
> **`pv`**: 【标量或 (M, 数组)】当前值
> **`when`**: 开始时默认值为 `{'end', 0}`

## 返回值

仅根据本金价值支付的金额。

## 正在求解的方程

> `Fv + PV * (1 + rate)**nper + pmt * (1 + rate * when) / rate * (1 + rate)**(nper - 1) = 0`
>
> 或者当 `rate == 0` 时：`Fv + PV + PMT * nper = 0`

## 代码示例

```py
# Python program explaining
# ppmt() function

import numpy as np

'''
Question :

monthly payment needed to pay off a $10, 000 loan
in 12 years at an annual interest rate of 10 %
'''

# rate     nper     pv
Solution = np.ppmt(0.10 / 12, 12 * 12, 10000)

# Here fv = 0 ; Also Default value of fv = 0
print("Solution : ", Solution)
```

## 输出

```py
Solution :  -0.1195078262827336
```