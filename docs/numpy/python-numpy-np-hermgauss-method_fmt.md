# Python | Numpy np.hermgauss()方法

> 原文链接：https://www.geeksforgeeks.org/python-numpy-np-hermgauss-method/

借助`np.hermgauss()`方法，可以得到高斯-埃尔米特求积的节点和权重。

## 语法
`np.hermgauss(degree)`

## 返回值
返回高斯-埃尔米特求积的节点和权重。

## 示例

### 例 1
在这个例子中，通过使用`np.hermgauss()`方法，我们能够得到高斯-埃尔米特求积的节点和权重。

```py
# import numpy and hermgauss
import numpy as np

# using np.hermgauss() method
gfg = np.hermgauss(3)

print(gfg)
```

**输出:**
```
(array([-1.22474487,  0.        ,  1.22474487]), array([0.29540898, 1.1816359 , 0.29540898]))
```

### 例 2

```py
# import numpy and hermgauss
import numpy as np

# using np.hermgauss() method
gfg = np.hermgauss(5)

print(gfg)
```

**输出:**
```
(array([-2.02018287, -0.95857246,  0.        ,  0.95857246,  2.02018287]), array([0.01995324, 0.39361932, 0.94530872, 0.39361932, 0.01995324]))
```