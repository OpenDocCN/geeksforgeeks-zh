# 如何使用 Bootstrap 5 在中心设置列？

> 原文:[https://www . geesforgeks . org/如何使用 bootstrap-5 设置中心列/](https://www.geeksforgeeks.org/how-to-set-column-in-center-using-bootstrap-5/)

这里的目标是在 bootstrap 中居中一列。Bootstrap 是一个免费的开源 CSS 框架，致力于响应性、移动优先的前端网络开发。在 Bootstrap 中有两种方法可以将列

居中。

**接近 1(偏移):**

第一种方法使用自举**偏移**类。关键是设置一个等于行剩余大小一半的偏移量。例如，大小为 2 的列将通过添加偏移量 5 来居中，即(12-2)/2。下面的示例实现了这一点。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <link rel="stylesheet"
          href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" 
          integrity=
"sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" 
          crossorigin="anonymous" />
    <body>
        <div class="container">
            <div class="row">
                <div style="height: 200px;" 
                     class="col-md-6 offset-md-3
                            text-center bg-success">.
                  col-md-6 .offset-md-3</div>
            </div>
        </div>
    </body>
</html>
```

**输出**

![](img/fc65b9d6346cbc8189cde2d9ff5b796a.png)

**进场 2(保证金自动):**

将左右边距设置为自动将使 div 相对于其父元素居中。左右边距可以用**设置。ml-auto** 和**。mr-auto** 类分别为。下面的示例实现了这一点。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <link rel="stylesheet" 
          href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
          integrity=
"sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" 
          crossorigin="anonymous" />
    <body>
        <div class="container">
            <div class="row">
                <div style="height: 200px;" 
                     class="mr-auto ml-auto 
                            text-center bg-success">
                  .ml-auto .mr-auto</div>
            </div>
        </div>
    </body>
</html>
```

**输出**

![](img/181ea7774b2c4b3dbe8b8ebca87fc492.png)