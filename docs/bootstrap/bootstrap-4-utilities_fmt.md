# 引导程序 4 | 实用程序

> 原文: [https://www.geeksforgeeks.org/bootstrap-4-utilities/](https://www.geeksforgeeks.org/bootstrap-4-utilities/)

对于不熟悉这个术语的人来说，`Bootstrap 4`是一个免费的前端框架，用于更快、更容易的网络开发。
Bootstrap 包括基于`[HTML](https://www.geeksforgeeks.org/html-tutorials/)`和`[CSS](https://www.geeksforgeeks.org/css-tutorials/)`的设计模板，用于*排版*、*表单*、*按钮*、*表格*、*导航*、*modals*、*图像转盘*和许多其他模板，以及可选的`JavaScript`。

Bootstrap 还让您能够轻松创建响应性设计。

## 用于布局的实用程序

为了更快的移动友好和响应性开发，Bootstrap 4 包括几十个用于显示、隐藏、对齐和间隔内容的实用程序类。所有这些都进行了分类，并列举了以下示例：

### 颜色

它们用于通过颜色实用程序类来传达含义。Bootstrap 4 还支持使用悬停状态（当您将光标移到项目上时的状态）来设置链接样式。

**示例 1:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet"
          href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>

<body>

<div class="container">
    <p class="text-primary">.text-primary</p>
    <p class="text-secondary">.text-secondary</p>
    <p class="text-success">.text-success</p>
    <p class="text-danger">.text-danger</p>
    <p class="text-warning">.text-warning</p>
    <p class="text-info">.text-info</p>
    <p class="text-light bg-dark">.text-light</p>
    <p class="text-dark">.text-dark</p>
    <p class="text-muted">.text-muted</p>
    <p class="text-white bg-dark">.text-white</p>
</div>

</body>

</html>
```

**输出:**
![](img/3a72e528984d7a025ec298423664f08a.png)

上下文文本类也可以用于链接，这将增加一个更深的悬停颜色。

**示例 2:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet"
          href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>

<body>

<div class="container">
    <h2>Contextual Link Colors</h2>
    <p>Hover over the links.</p>
    <a href="#" class="text-muted">
        Muted link.
    </a>
    <a href="#" class="text-primary">
        Primary link.
    </a>
    <a href="#" class="text-success">
        Success link.
    </a>
    <a href="#" class="text-info">
        Info link.
    </a>
    <a href="#" class="text-warning">
        Warning link.
    </a>
    <a href="#" class="text-danger">
        Danger link.
    </a>
    <a href="#" class="text-secondary">
        Secondary link.
    </a>
    <a href="#" class="text-dark">
        Dark grey link.
    </a>
    <a href="#" class="text-body">
        Body/black link.
    </a>
    <a href="#" class="text-light">
        Light grey link.
    </a>
</div>

</body>

</html>
```

**输出:**
![](img/74031b3ecd4460ca01faa9fbffa35723.png)

在这里，当我们悬停在上面代码中的文本（链接）上时，会出现更深的颜色。
我们还可以使用`.text-black-50`或`.text-white-50`类为黑色或白色文本添加 5% 的不透明度，如下所示：

**示例 3:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet"
          href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>

<body>

<div class="container">
    <p class="text-black-50">
        Black text with 50% opacity on white background
    </p>
    <p class="text-white-50 bg-dark">
        White text with 50% opacity on black background
    </p>
</div>

</body>

</html>
```

**输出:**
![](img/d1d39b2ca14322b8bec7125c610e93b2.png)

### 背景颜色

与上下文文本颜色类类似，我们可以轻松地将元素的背景设置为任何上下文类。用于背景颜色的类有：`.bg-primary`、`.bg-success`、`.bg-info`、`.bg-warning`、`.bg-danger`、`.bg-secondary`、`.bg-dark`和`.bg-light`。

**注意:** 背景色不设置文字颜色，所以在某些情况下你会想要和`.text-*`类一起使用。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet"
          href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>

<body>

<div class="container">
    <p class="bg-primary text-white">
        This text is important.
    </p>
    <p class="bg-success text-white">
        This text indicates success.
    </p>
    <p class="bg-info text-white">
        This text represents some information.
    </p>
    <p class="bg-warning text-white">
        This text represents a warning.
    </p>
    <p class="bg-danger text-white">
        This text represents danger.
    </p>
    <p class="bg-secondary text-white">
        Secondary background color.
    </p>
    <p class="bg-dark text-white">
        Dark grey background color.
    </p>
    <p class="bg-light text-dark">
        Light grey background color.
    </p>
</div>

</body>

</html>
```

**输出:**
![](img/c96eed27380a84ed02a771bb87af1435.png)

### 边框工具

它们用于添加或移除元素的边框。使用边框工具快速设置元素的边框和边框半径的样式。适用于图像、按钮或任何其他元素。在这里使用`.border`类。

1.  **添加边框:** 用于“添加”边框。
    **示例:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet"
          href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <style>
        .border {
            display: inline-block;
            width: 70px;
            height: 70px;
            margin: 6px;
        }
    </style>
</head>

<body>

<div class="container">
    <span class="border"></span>
    <span class="border border"></span>
    <span class="border border-top"></span>
    <span class="border border-right"></span>
    <span class="border border-bottom"></span>
    <span class="border border-left"></span>
</div>

</body>

</html>
```

**输出:**
![](img/3a0f94140b4c30a900143fc9ee5d7c8f.png)

可以看到，所有 4 个边框都被添加到第一个方块中，然后顶部、右侧、底部和左侧的边框被添加到后面的方块中，如上面的代码所示。(边框较轻，仔细观察)

2.  **减法边框:** 用于*移除*边框。
    **示例:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet"
          href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <style>
        .border {
            display: inline-block;
            width: 70px;
            height: 70px;
            margin: 6px;
        }
    </style>
</head>

<body>

<div class="container">
    <span class="border"></span>
    <span class="border border-0"></span>
    <span class="border border-top-0"></span>
    <span class="border border-right-0"></span>
    <span class="border border-bottom-0"></span>
    <span class="border border-left-0"></span>
</div>

</body>

</html>
```

**输出:**
![](img/a1c04da9c73d87791bbfd1eedb9c4ff6.png)

从上面提供的图片中可以再次清楚地看到，所有 4 个边框都从第一个方块中移除，然后顶部、右侧、底部和左侧的边框也从随后的方块中移除(从最初的 4 边带边框的方块中)，如上面的代码所示。(边框是浅色的，仔细观察)
注意，我们只需在代码中添加一个`-0`(在`.border`之后)，使其减色。

3.  **边框颜色:** 用于给边框指定特定颜色。
    **示例:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet"
          href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <style>
        .border {
            display: inline-block;
            width: 70px;
            height: 70px;
            margin: 6px;
        }
    </style>
</head>

<body>
```

## 边框颜色

上面的例子很简单，边框颜色通常表示危险，比如红色表示危险，黄色表示警告(如警告街道标志)，绿色表示成功，等等。

## 圆角

使用圆角可以给元素特定的半径类型（例如圆形边缘）。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" 
          href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <style>
        span {
            display: inline-block;
            width: 70px;
            height: 70px;
            margin: 6px;
            background-color: #555;
        }
    </style>
</head>

<body>

<div class="container">
        <span class="rounded-sm">
      </span>
        <span class="rounded">
      </span>
        <span class="rounded-lg">
      </span>
        <span class="rounded-top">
      </span>
        <span class="rounded-right">
      </span>
        <span class="rounded-bottom">
      </span>
        <span class="rounded-left">
      </span>
        <span class="rounded-circle">
      </span>
        <span class="rounded-0">
      </span>
    </div>

</body>

</html>
```

**输出:**
![](img/352075c5ea92a8be7c98c003586daa6f.png)

在上面的例子中，我们在前三个正方形的所有 4 边上添加了圆角(拐角分别是小的、正常的和大的)，然后只添加了后续正方形的顶部、右侧、底部和左侧，从上面的代码中可以明显看出。然后实现完全圆形边框(不是正方形、圆形)和非圆形边框(正方形、没有圆形边缘)。

## 文本

Bootstrap 4 包括用于控制对齐、环绕、粗细等常用文本实用程序的文档和示例。

### 文本对齐

对于左对齐、右对齐和居中对齐，提供了响应式类，这些类使用与网格系统相同的视口宽度断点。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" 
          href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>

<body>

<div class="container">
        <p class="text-left">
          Left aligned text on all viewport sizes.
      </p>
        <p class="text-center">
          Center aligned text on all viewport sizes.
      </p>
        <p class="text-right">
          Right aligned text on all viewport sizes.
      </p>

<p class="text-sm-left">
          Left aligned text on viewports sized SM 
          (small) or wider.
      </p>
        <p class="text-md-left">
          Left aligned text on viewports sized MD
          (medium) or wider.
      </p>
        <p class="text-lg-left">
          Left aligned text on viewports sized LG
          (large) or wider.
      </p>
        <p class="text-xl-left">
          Left aligned text on viewports sized XL
          (extra-large) or wider.
      </p>
    </div>

</body>

</html>
```

**输出:**
![](img/fb21be4348a0f038cc24c31c17254caa.png)

### 文本转换

我们可以使用文本大写类来转换组件中的文本。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" 
          href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>

<body>

<div class="container">
        <p class="text-lowercase">Lowercased text.</p>
        <p class="text-uppercase">Uppercased text.</p>
        <p class="text-capitalize">Capitalized text.</p>
    </div>
</body>

</html>
```

**输出:**
![](img/b1b9d8b593c50bf59e5530b0eb1d6234.png)

### 字体粗细/斜体

我们可以改变文本的粗细/粗体或使文本倾斜。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" 
          href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>

<body>

<div class="container">
        <h1>Font weight and italics</h1>
        <p class="font-weight-bold">
          Bold text.
      </p>
        <p class="font-weight-normal">
          Normal weight text.
      </p>
        <p class="font-weight-light">
          Light weight text.
      </p>
        <p class="font-italic">
          Italic text.
      </p>
    </div>
</body>

</html>
```

**输出:**
![](img/82e9bbf577d1aeacae8fd63c2b097146.png)

## 浮动和清除工具

我们可以用`float-left`将一个元素向左浮动。与`float-right`类似，向右浮动。`float-none`级或向左浮动。`clearfix`类。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" 
          href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>

<body>
    <div class="container">
        <div class="clearfix">
            <span class="float-left">
              Float left
          </span>
            <span class="float-right">
              Float right
          </span>
        </div>
    </div>

</body>

</html>
```

**输出:**
![](img/47a1d48eb62a630e44c8057eb1abec2f.png)

我们可以用`clearfix`类清除浮漂。

### 响应式浮动

我们可以根据屏幕宽度将元素向左或向右浮动，使用响应式浮动类 (`float-*-left|right` – 其中 * 是 sm (>=576px), md (>=768px), lg (>=992px) 或 xl (>=1200px))。这些不同类别（小、中、大、特大）的大小是固定的。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" 
          href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>

<body>
    <div class="container">
        <div class="clearfix">
            <div class="float-sm-right">
              Float right on small screens or wider
          </div>
            <br>
            <div class="float-md-right">
              Float right on medium screens or wider
          </div>
            <br>
            <div class="float-lg-right">
              Float right on large screens or wider
          </div>
            <br>
            <div class="float-xl-right">
              Float right on extra large screens or wider
          </div>
            <br>
            <div class="float-none">
              Float none
          </div>
        </div>
    </div>
</body>

</html>
```

**输出:**
![](img/628d99affc17cacd397903bd026b5d7f.png)

## 定位

有一些简写工具用于快速配置元素的位置。一些快速定位类是 `position-static`、`position-relative`、`position-absolute`、`position-fixed` 和 `position-sticky`。

例如，我们可以使用 `fixed-top` 类使任何元素固定/停留在页面顶部。
同样，`fixed-bottom` 类将一个元素定位在视口的底部，从一边到另一边。
`sticky-top` 会将一个元素从一条边到另一条边放置在视口的顶部，但前提是你要经过它。`sticky-top` 实用程序使用了 CSS 的 `position: sticky`，这并不是所有浏览器都完全支持的。同样，`sticky-bottom` 对底面也是如此。

# 尺寸

Bootstrap 4 使我们能够使用元素的宽度和高度实用程序轻松地使元素与它的父元素一样宽或一样高。

## 宽度

使用 `w-*` 类（`.w-25`, `.w-50`, `.w-75`, `.w-100`, `.mw-100`）设置元素的宽度。

**示例：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
<div class="container">
    <div class="w-25 bg-success">
        Width 25%
    </div>
    <div class="w-50 bg-success">
        Width 50%
    </div>
    <div class="w-75 bg-success">
        Width 75%
    </div>
    <div class="w-100 bg-success">
        Width 100%
    </div>
    <div class="mw-100 bg-success">
        Max Width 100%
    </div>
</div>
</body>
</html>
```

**输出：**
![](img/bf869dcd10e25db9331417bb6c52ec6e.png)

## 高度

使用 `h-*` 类（`.h-25`, `.h-50`, `.h-75`, `.h-100`, `.mh-100`）设置元素的高度。

**示例：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
<div class="container">
    <div style="height:200px;background-color:#ddd">
        <div class="h-25 d-inline-block p-2 bg-success">
            Height 25%
        </div>
        <div class="h-50 d-inline-block p-2 bg-success">
            Height 50%
        </div>
        <div class="h-75 d-inline-block p-2 bg-success">
            Height 75%
        </div>
        <div class="h-100 d-inline-block p-2 bg-success">
            Height 100%
        </div>
        <div class="mh-100 d-inline-block p-2 bg-success" style="height:500px">
            Max Height 100%
        </div>
    </div>
</div>
</body>
</html>
```

**输出：**
![](img/07fdb48b89ffc9ec7d73264208ed0772.png)

# 间距

Bootstrap 4 提供了广泛的响应式边距和填充实用类。它们适用于所有断点（类名中没有断点缩写）：xs (=576px), md (>=768px), lg (>=992px) 或 xl (>=1200px)。

这些类的格式为：对于 xs（超小型）是 `{property}{sides}-{size}`，对于 sm、md、lg 和 xl 是 `{property}{sides}-{breakpoint}-{size}`。

其中属性为：
- `m` – 设置边距
- `p` – 设置填充

其中边为：
- `t` – 设置边距顶部或填充顶部
- `b` – 设置边距底部或填充底部
- `l` – 设置边距左侧或填充左侧
- `r` – 设置边距右侧或填充右侧
- `x` – 设置边距左侧和右侧或填充左侧和右侧
- `y` – 设置边距顶部和底部或填充顶部和底部

大小为：
- `0` – 将边距或填充设置为 0
- `1` – 将边距或填充设置为 `.25rem`（如果字体大小为 16px，则为 4px）
- `2` – 将边距或填充设置为 `.5rem`（如果字体大小为 16px，则为 8px）
- `3` – 将边距或填充设置为 `1rem`（如果字体大小为 16px，则为 16px）
- `4` – 将边距或填充设置为 `1.5rem`（如果字体大小为 16px，则为 24px）
- `5` – 将边距或填充设置为 `3rem`（如果字号为 16px，则为 48px）
- `auto` – 将边距设置为 auto

**注意：** 边距也可以是负数，在字号前面加一个 `"n"`。
- `n1` – 将边距设置为 `-.25rem`（-4px，如果字号为 16px）
- `n2` – 将边距设置为 `-.5rem`（-8px，如果字号为 16px）
- `n3` – 将边距设置为 `-1rem`（-16px，如果字号为 16px）
- `n4` – 将边距设置为 `-1.5rem`（-24px，如果字号为 16px）

**示例：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
<div class="container">
    <div class="pt-4 bg-info">
        I only have a top padding (1.5rem = 24px)
    </div>
    <div class="p-5 bg-success">
        I have a padding on all sides (3rem = 48px)
    </div>
    <div class="m-5 pb-5 bg-info">
        I have a margin on all sides (3rem = 48px) and a bottom padding (3rem = 48px)
    </div>
</div>
</body>
</html>
```

**输出：**
![](img/6fb941f9184a3700e85ad18ac3b92174.png)

**更多间距示例：**

# 间距工具类

| 类名 | 描述 |
| :--- | :--- |
| `.m-#` / `.m-*-#` | 四面空白 |
| `.mt-#` / `.mt-*-#` | 上边距 |
| `.mb-#` / `.mb-*-#` | 边距底部 |
| `.ml-#` / `.ml-*-#` | 左边距 |
| `.mr-#` / `.mr-*-#` | 右边距 |
| `.mx-#` / `.mx-*-#` | 左右边距 |
| `.my-#` / `.my-*-#` | 上边距和下边距 |

| 类名 | 描述 |
| :--- | :--- |
| `.p-#` / `.p-*-#` | 四面都有衬垫 |
| `.pt-#` / `.pt-*-#` | 填充顶部 |
| `.pb-#` / `.pb-*-#` | 填充底部 |
| `.pl-#` / `.pl-*-#` | 左填充 |
| `.pr-#` / `.pr-*-#` | 向右填充 |
| `.py-#` / `.py-*-#` | 填充顶部和底部 |
| `.px-#` / `.px-*-#` | 左右填充 |

# 阴影

使用`shadow`类为元素添加阴影。

**例:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
<div class="container">
    <div class="shadow-none p-4 mb-4 bg-light">
        No shadow
    </div>
    <div class="shadow-sm p-4 mb-4 bg-white">
        Small shadow
    </div>
    <div class="shadow p-4 mb-4 bg-white">
        Default shadow
    </div>
    <div class="shadow-lg p-4 mb-4 bg-white">
        Large shadow
    </div>
</div>
</body>
</html>
```

**输出:**
![](img/a9b5182c061f3906be2111d4c4b9e7eb.png)

# 垂直对齐

Bootstrap 4 使用`align`类来更改元素的对齐方式（仅适用于内联、内联块、内联表格和表格单元格元素）。我们可以从`.align-baseline`、`.align-top`、`.align-middle`、`.align-bottom`、`.align-text-bottom`和`.align-text-top`中根据需要选择。

## 内联元素

**例如:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
<div class="container">
    <span class="align-baseline">
        baseline
    </span>
    <span class="align-top">
        top
    </span>
    <span class="align-middle">
        middle
    </span>
    <span class="align-bottom">
        bottom
    </span>
    <span class="align-text-top">
        text-top
    </span>
    <span class="align-text-bottom">
        text-bottom
    </span>
</div>
</body>
</html>
```

**输出:**
![](img/99d50fc40be427c7510fd6111caef0ab.png)

## 表格单元格

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
<div class="container">
    <table style="height: 100px;">
        <tbody>
            <tr>
                <td class="align-baseline">
                    baseline
                </td>
                <td class="align-top">
                    top
                </td>
                <td class="align-middle">
                    middle
                </td>
                <td class="align-bottom">
                    bottom
                </td>
                <td class="align-text-top">
                    text-top
                </td>
                <td class="align-text-bottom">
                    text-bottom
                </td>
            </tr>
        </tbody>
    </table>
</div>
</body>
</html>
```

**输出:**
![](img/bb316b9e3beb405656b0266e468fa4e8.png)

# 嵌入

Bootstrap 4 使我们能够基于父元素的宽度创建响应式视频或幻灯片嵌入，通过创建一个在任何设备上都能按比例缩放的固有比率。我们只需将`.embed-responsive-item`添加到任何嵌入元素中，该元素需位于具有`.embed-responsive`类和我们选择的宽高比的父元素内。

**Example:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
<div class="container mt-3">
    <p>Create a responsive video and scale it nicely to the parent element.</p>
    <h2>Aspect ratio 1:1</h2>
    <div class="embed-responsive embed-responsive-1by1">
        <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/MtQL_ll5KhQ"></iframe>
    </div>
    <br>
    <h2>Aspect ratio 4:3</h2>
    <div class="embed-responsive embed-responsive-4by3">
        <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/MtQL_ll5KhQ"></iframe>
    </div>
    <br>
    <h2>Aspect ratio 16:9</h2>
    <div class="embed-responsive embed-responsive-16by9">
        <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/MtQL_ll5KhQ"></iframe>
    </div>
    <br>
    <h2>Aspect ratio 21:9</h2>
    <div class="embed-responsive embed-responsive-21by9">
        <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/MtQL_ll5KhQ"></iframe>
    </div>
</div>
</body>
</html>
```

**输出:**
![](img/f31006289b2c668ebe436ff7e29020d3.png)

在上面的代码中，将标签`` `tgbNymZ7vqY` ``替换为您想要的 youtube 视频或您选择的视频 URL，以防您想要不同的视频。(或更改其他视频托管/共享网站的完整网址)

## Visibility
我们可以使用可见性实用工具控制元素的可见性，而不修改其显示。只需使用`` `.visible` ``或`` `.invisible` ``类来控制元素的可见性。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
    <div class="container">
        <div class="visible bg-success">
            I am visible
        </div>
        <div class="invisible bg-warning">
            I am invisible
        </div>
    </div>
</body>
</html>
```

**输出:**
![](img/21ef45045e44ed26ab5d9da8bb4860e3.png)

## Close Icon
我们可以使用`` `.close` ``类来设置关闭图标的样式。这通常用于关闭警报和模态框。

**注意:** 我们使用 **×** 符号来创建实际的图标(更好看的“x”)。还要注意的是，默认情况下它会向右浮动。

**示例:**
(关闭时显示为空白/白色)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
    <div class="container">
        <div class="clearfix">
            <button type="button" class="close">
                ×
            </button>
        </div>
    </div>
</body>
</html>
```

**输出:**
![](img/78a0dc690a99066f1f1e10b838dc1476.png)

## Screenreaders
我们可以使用屏幕阅读器实用工具(``.sr-only``)在除屏幕阅读器外的所有设备上隐藏元素。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
<div class="container mt-3">
    <p>Use the .sr-only class to hide an element on all devices, except screen readers:</p>
    <span class="sr-only">
        I will be hidden on all screens except for screen readers.
    </span>
</div>
</body>
</html>
```

**输出:**

## Blocks
要将元素变为块级元素，请添加`` `.d-block` ``类。我们可以使用任何`` `d-*-block` ``类来控制**何时**元素应在特定屏幕宽度下成为块级元素。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
<div class="container mt-3">
    <span class="d-block bg-success">d-block</span>
    <span class="d-sm-block bg-success">d-sm-block</span>
    <span class="d-md-block bg-success">d-md-block</span>
    <span class="d-lg-block bg-success">d-lg-block</span>
    <span class="d-xl-block bg-success">d-xl-block</span>
</div>
</body>
</html>
```

**输出:**
![](img/364efc46061e4f27f612711e57018923.png)

## Flex
Bootstrap 4 通过一整套响应灵敏的 flexbox 实用程序，帮助我们快速管理网格列、导航、组件等的布局、对齐和大小调整。对于更复杂的实现，自定义 CSS 可能是必要的。我们可以用`` `.flex-*` ``类使用 flexbox 控制布局。

### Flex Behaviors
我们可以应用显示实用程序来创建 flex 容器，并将直接子元素转换为 flex 项目。容器和项目可以通过额外的 flex 属性进行进一步修改。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
    <div class="container mt-3">
        <div class="d-flex p-2">I'm a flexbox container!</div>
        <div class="d-inline-flex p-2">I'm an inline flexbox container!</div>
    </div>
</body>
</html>
```

**输出:**
![](img/acbfe1b403638ff8b26bc6711d8b5f54.png)
![](img/3bf3c05134dba94f37d5ea058dcd63e6.png)

### Direction
我们可以在带有方向工具的 flex 容器中设置 flex 项目的方向。在大多数情况下，您可以省略水平类，因为浏览器默认为一行。但是，您可能会遇到需要显式设置该值的情况(如响应布局)。
使用`` `.flex-row` ``设置水平方向(浏览器默认)或`` `.flex-row-reverse` ``从对面开始水平方向。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
    <div class="container mt-3">
        <div class="d-flex flex-row">
            <div class="p-2">Flex item 1</div>
            <div class="p-2">Flex item 2</div>
            <div class="p-2">Flex item 3</div>
        </div>
        <div class="d-flex flex-row-reverse">
            <div class="p-2">Flex item 1</div>
            <div class="p-2">Flex item 2</div>
            <div class="p-2">Flex item 3</div>
        </div>
    </div>
</body>
</html>
```

**输出:**
![](img/b004a6d48aa925cd11eb197a6c956c0d.png)

同样，我们可以使用`` `.flex-column` ``设置垂直方向，或使用`` `.flex-column-reverse` ``从相反一侧开始垂直方向。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
```

# Bootstrap Flexbox 和 Display 工具类指南

## Flex 方向

我们可以使用 `flex-column` 和 `flex-column-reverse` 工具类来改变 flex 项目的排列方向。

```html
<div class="container mt-3">
    <div class="d-flex flex-column">
        <div class="p-2">
            Flex item 1
        </div>
        <div class="p-2">
            Flex item 2
        </div>
        <div class="p-2">
            Flex item 3
        </div>
    </div>
    <div class="d-flex flex-column-reverse">
        <div class="p-2">
            Flex item 1
        </div>
        <div class="p-2">
            Flex item 2
        </div>
        <div class="p-2">
            Flex item 3
        </div>
    </div>
</div>
```

**输出:**
![](img/44867132b1ef2db9a1eb3194cc65be53.png)

## 对齐

我们可以在 flex 容器上使用 `justify-content` 工具类来改变 flex 项目在主轴（初始为 x 轴，如果 `flex-direction: column` 则为 y 轴）上的对齐方式。可选值有 `start`（浏览器默认）、`end`、`center`、`between` 或 `around`。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
    <div class="container mt-3">
        <div class="d-flex justify-content-start bg-secondary mb-3">
            <div class="p-2 bg-success">Flex item 1</div>
            <div class="p-2 bg-success">Flex item 2</div>
            <div class="p-2 bg-success">Flex item 3</div>
        </div>
        <div class="d-flex justify-content-end bg-secondary mb-3">
            <div class="p-2 bg-success">Flex item 1</div>
            <div class="p-2 bg-success">Flex item 2</div>
            <div class="p-2 bg-success">Flex item 3</div>
        </div>
        <div class="d-flex justify-content-center bg-secondary mb-3">
            <div class="p-2 bg-success">Flex item 1</div>
            <div class="p-2 bg-success">Flex item 2</div>
            <div class="p-2 bg-success">Flex item 3</div>
        </div>
        <div class="d-flex justify-content-between bg-secondary mb-3">
            <div class="p-2 bg-success">Flex item 1</div>
            <div class="p-2 bg-success">Flex item 2</div>
            <div class="p-2 bg-success">Flex item 3</div>
        </div>
        <div class="d-flex justify-content-around bg-secondary mb-3">
            <div class="p-2 bg-success">Flex item 1</div>
            <div class="p-2 bg-success">Flex item 2</div>
            <div class="p-2 bg-success">Flex item 3</div>
        </div>
    </div>
</body>
</html>
```

**输出:**
![](img/e3d2e7e7468c160db5276e6eb7dbed1d.png)

## 排序

我们还可以使用少量的排序工具类来更改特定 flex 项目的视觉顺序。我们只提供了让一个项目成为第一个或最后一个的选项，以及使用 DOM 顺序的重置。当 `order` 取任何整数值（例如 `5`）时，为任何需要的附加值添加自定义 CSS。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
    <div class="container mt-3">
        <div class="d-flex mb-3">
            <div class="p-2 order-3 bg-success">Flex item 1</div>
            <div class="p-2 order-2 bg-success">Flex item 2</div>
            <div class="p-2 order-1 bg-success">Flex item 3</div>
        </div>
    </div>
</body>
</html>
```

**输出:**
![](img/2f8c283c7d1e1a90c51306817dc6f330.png)

## 显示

最后，我们可以使用响应式显示工具类来改变 `display` 属性的值。Bootstrap 4 有意只支持所有可能显示值的一个子集。类可以根据需要组合以实现各种效果。

因此，类的命名格式如下：
- 对于 xs 屏幕：`.d-{value}`
- 对于 sm, md, lg, 和 xl 屏幕：`.d-{breakpoint}-{value}`

**其中值为以下之一：**
- `none`
- `inline`
- `inline-block`
- `block`
- `table`
- `table-cell`
- `table-row`
- `flex`
- `inline-flex`

**示例:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
    <div class="d-inline p-2 bg-primary text-white">d-inline</div>
    <div class="d-inline p-2 bg-dark text-white">d-inline</div>
</body>
</html>
```

**输出:**
![](img/6e047d4faa93fe327eac73fccce686b7.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
</head>
<body>
    <span class="d-block p-2 bg-primary text-white">d-block</span>
    <span class="d-block p-2 bg-dark text-white">d-block</span>
</body>
</html>
```

**输出:**
![](img/2049f72a68a08e94dbeb037dd74f5210.png)

此外，要隐藏元素，我们只需使用 `.d-none` 类或者 `.d-{sm, md, lg, xl}-none` 类来响应屏幕尺寸变化。
同样，为了仅在给定的屏幕尺寸间隔上显示元素，我们可以组合一个 `.d-*-none` 类和 `.d-*-**` 类，例如 `.d-none`、`.d-md-block`、`.d-xl-none` 将隐藏除中大型设备外的所有屏幕尺寸的元素。