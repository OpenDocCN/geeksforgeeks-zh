# Python 中的 colorsys 模块示例

> 原文：[https://www.geeksforgeeks.org/colorsys-module-in-python-with-examples/](https://www.geeksforgeeks.org/colorsys-module-in-python-with-examples/)

Python 中的 `colorsys` 模块定义了 RGB（红绿蓝）颜色与其他三个坐标 YIQ（亮度（Y）同相正交）、HLS（色相明度饱和度）和 HSV（色相饱和度值）之间的颜色值双向转换。

## colorsys 模块定义的函数

*   `colorsys.rgb_to_yiq(r, g, b)`：将颜色从 RGB 坐标转换为 YIQ 坐标。
*   `colorsys.yiq_to_rgb(y, i, q)`：将颜色从 YIQ 坐标转换为 RGB 坐标。
*   `colorsys.rgb_to_hls(r, g, b)`：将颜色从 RGB 坐标转换为 HLS 坐标。
*   `colorsys.hls_to_rgb(h, l, s)`：将颜色从 HLS 坐标转换为 RGB 坐标。
*   `colorsys.rgb_to_hsv(r, g, b)`：将颜色从 RGB 坐标转换为 HSV 坐标。
*   `colorsys.hsv_to_rgb(h, s, v)`：将颜色从 HSV 坐标转换为 RGB 坐标。

除 `colorsys.yiq_to_rgb()` 外，上述所有函数都接受范围在 0 到 1 之间的浮点值作为参数。在函数 `colorsys.yiq_to_rgb(y, i, q)` 中，参数 `y` 是 0 到 1 范围内的浮点值，参数 `i` 和 `q` 也接受 0 到 1 范围内的浮点值，但可以是正的也可以是负的。

上述所有函数都返回一个元组，该元组表示结果坐标。

## 代码示例

### 代码 #1：将颜色从 RGB 坐标转换为 YIQ 坐标

```py
# Python program to explain colorsys.rgb_to_yiq() method

# importing colorsys module 
import colorsys

# Define RGB coordinates
r = 0.2
g = 0.4
b = 0.4

# Convert the color from RGB 
# coordinates to YIQ coordinates
yiq = colorsys.rgb_to_yiq(r, g, b)

# Print the yiq coordinates
print(yiq)
```

**输出：**

```py
(0.33999999999999997, -0.11979999999999999, -0.04259999999999996)
```

### 代码 #2：将颜色从 YIQ 坐标转换为 RGB 坐标

```py
# Python program to explain colorsys.yiq_to_rgb() method

# importing colorsys module 
import colorsys

# Define YIQ coordinates
y = 0.34
i = -0.12
q = -0.04

# Convert the color from RGB 
# coordinates to YIQ coordinates
rgb = colorsys.yiq_to_rgb(y, i, q)

# Print the RGB coordinates
print(rgb)
```

**输出：**

```py
(0.20143187066974597, 0.3984021607233726, 0.40466512702078516)
```

### 代码 #3：将颜色从 RGB 坐标转换为 HLS 坐标

```py
# Python program to explain colorsys.rgb_to_hls() method

# importing colorsys module 
import colorsys

# Define RGB coordinates
r = 0.2
g = 0.4
b = 0.4

# Convert the color from RGB 
# coordinates to HLS coordinates
hls = colorsys.rgb_to_hls(r, g, b)

# Print the HLS coordinates
print(hls)
```

**输出：**

```py
(0.5, 0.30000000000000004, 0.3333333333333333)
```

### 代码 #4：将颜色从 HLS 坐标转换为 RGB 坐标

```py
# Python program to explain colorsys.hls_to_rgb() method

# importing colorsys module 
import colorsys

# Define HLS coordinates
h = 0.2
l = 0.7
s = 0.5

# Convert the color from HLS 
# coordinates to RGB coordinates
rgb = colorsys.hls_to_rgb(h, l, s)

# Print the RGB coordinates
print(rgb)
```

**输出：**

```py
(0.7899999999999999, 0.85, 0.5499999999999999)
```

### 代码 #5：将颜色从 RGB 坐标转换为 HSV 坐标

```py
# Python program to explain colorsys.rgb_to_hsv() method

# importing colorsys module 
import colorsys

# Define RGB coordinates
r = 0.2
g = 0.4
b = 0.4

# Convert the color from RGB 
# coordinates to HSV coordinates
hsv = colorsys.rgb_to_hsv(r, g, b)

# Print the HSV coordinates
print(hsv)
```

**输出：**

```py
(0.5, 0.5, 0.4)
```

### 代码 #6：将颜色从 HSV 坐标转换为 RGB 坐标

```py
# Python program to explain colorsys.hsv_to_rgb() method

# importing colorsys module 
import colorsys

# Define HSV coordinates
h = 0.5
s = 0.5
v = 0.4

# Convert the color from HSV 
# coordinates to RGB coordinates
rgb = colorsys.hsv_to_rgb(h, s, v)

# Print the RGB coordinates
print(rgb)
```

**输出：**

```py
(0.2, 0.4, 0.4)
```