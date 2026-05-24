# Python–魔杖中的`distort()`方法

> 原文: [https://www.geeksforgeeks.org/python-distort-method-in-wand/](https://www.geeksforgeeks.org/python-distort-method-in-wand/)

ImageMagick 通过对用户提供的参数应用各种转换，提供了几种扭曲图像的方法。在魔杖中，使用了`distort()`的方法，并遵循一个基本函数。

## 语法

```py
wand.image.distort(method, arguments, best_fit)
```

## 参数

| 参数 | 输入类型 | 描述 |
| --- | --- | --- |
| `method` | 基绳 | 黑点，占系统量子范围的百分比。默认为 0.. |
| `arguments` | 集合. abc .序列 | `distort_method`中的失真方法名称。 |
| `best_fit` | 弯曲件 | 尝试调整结果图像的大小以适应失真。默认值为假。 |

## 变形方法

| 失真方法 | 描述 |
| --- | --- |
| `'undefined'` | 默认失真方法 |
| `'affine'` | 平行型失真。 |
| `'affine_projection'` | 一种 3 平行四边形投影。 |
| `'scale-rotate-translate'` | 转换失真 |
| `'perspective'` | 三维向外投影失真。 |
| `'perspective-projection'` | 创造一个遥远的视角。 |
| `'bilinear-forward'` | 基于双线性方程。 |
| `'bilinear-reverse'` | 基于反向双线性方程。 |
| `'polynomial'` | 基于多项式。 |
| `'arc'` | 创建图像的圆形曲线。 |
| `'polar'` | 创建极轴扭曲效果。 |
| `'depolar'` | 产生去极化失真效果。 |
| `'cylinder2plane'` | 创建圆柱体到平面的变形效果。 |
| `'plane2cylinder'` | 创建平面到圆柱体的变形效果。 |
| `'barrel'` | 在二维图像上创建向外凸起。 |
| `'barrel_inverse'` | 在二维图像上创建向内凸起。 |
| `'resize'` | 调整失真图像的大小。 |
| `'sentinel'` | 造成哨兵图像失真。 |

## 来源图片

![](img/3b4ee0698acd658ee9bd4a16ab6c636a.png)

## 代码示例 1

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="gog.png") as img:
    img.distort('arc', (45, ))
    img.save(filename ='gogdistort1.png')
```

**输出图像:**

![](img/99621edb52da44e87edd091d7507cf74.png)

## 代码示例 2

将`distort_method`更改为`'perspective'`。

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="gog.png") as img:
    arguments = (0, 0, 20, 60,
                 90, 0, 70, 63,
                 0, 90, 5, 83,
                 90, 90, 85, 88)
    img.distort('perspective', arguments)
    img.save(filename ='gogdistort.png')
```

**输出图像:**

![](img/9b72fcf6132d0688de48a195e578b1cd.png)