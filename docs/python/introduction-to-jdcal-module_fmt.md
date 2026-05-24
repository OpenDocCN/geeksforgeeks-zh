# jdcal 模块介绍

> 原文:[https://www.geeksforgeeks.org/introduction-to-jdcal-module/](https://www.geeksforgeeks.org/introduction-to-jdcal-module/)

Python 有一个将儒略历转换为公历的包，叫做 [jdcal](https://pypi.org/project/jdcal/) 。它大大简化了两个系统之间的转换，只需几行代码就足以实现该功能。

jdcal 中主要有四个功能:

*   `gcal2jd`: 将公历转换为儒略日。接受年、月、日作为整数参数，并返回两个浮点数的元组。
*   `jd2gcal`: 将儒略日转换为公历。接受两个整数作为参数，并返回一个包含年（整数）、月（整数）、日（整数）和公历日小数部分（浮点数）的四元素元组。
*   `jcal2jd`: 将儒略历日期转换为儒略日。接受所有整数值作为参数数组，并返回一个浮点数元组。
*   `jd2jcal`: 将儒略日转换为儒略历日期。返回一个包含年（整数）、月（整数）、日（整数）和儒略历日中小数部分（浮点数）格式的四元素元组。

## 安装

要安装，请在您的终端中运行以下命令

```py
pip install jdcal
```

## 实施

### 示例 1: gcal2jd

### Python 3

```py
# import module
import jdcal as j

# declare function
a= j.gcal2jd(2020, 12, 15) 
print(a) 
```

**输出:**

> (2400000.5，59198.0)

### 示例 2: jd2gcal

### Python 3

```py
# import module
import jdcal as j

# declare function
b= j.jd2gcal(2400000.5, 59198.0)

print(b)
```