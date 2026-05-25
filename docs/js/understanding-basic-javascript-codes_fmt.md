# 理解基本的 JavaScript 代码

> 原文：[https://www.geeksforgeeks.org/understanding-basic-javascript-codes/](https://www.geeksforgeeks.org/understanding-basic-javascript-codes/)

在网页中插入 JavaScript 很像插入任何其他的 HTML 内容。HTML 中用来添加 JavaScript 的标签是 `<script>`。被 `<script>` 标签包围的代码称为脚本块。
`<script>` 标签可以放在 `<head>` 和 `</head>` 标签之间或者 `<body>` 和 `</body>` 标签之间。

`type` 属性是 `<script>` 标签最重要的属性。然而，它现在不再被使用。浏览器能识别 `<script>` 标签里面是 JavaScript 代码。

```
<script type="text/javascript">
```

## 如何编写、保存和运行代码

**方法一：**
1.  使用任何文本编辑器如 `记事本`、`记事本++` 来编写代码。
2.  用 `.html` 扩展名保存文件，并加载到网页浏览器中。

**方法二：**
1.  创建一个 `.js` 文件，并使用您最喜欢的编辑器在这个文件中编写您的 JS 代码。
2.  在 HTML 文件内的 `<body>` 标签末尾添加 `<script src="relative_path_to_file/file_name.js"></script>`。

## 将页面涂成淡蓝色的代码

```
<!DOCTYPE html>
<html>
  <head>
    <title></title>
  </head>
  <body bgcolor="white">
   <p>Paragraph 1</p>
   <script type="text/javascript">
   document.bgColor ="lightblue";
   </script>
  </body>
<html>
```

输出：
![](img/1ed5f78439984999012835821f589d0f.png)

网页的颜色是浅蓝色，但是开始的 `<body>` 标签被定义为将背景颜色设置为白色。

```
<body bgcolor="white">
```

页面的背景颜色是浅蓝色，因为 JavaScript 用于将文档的背景颜色设置为浅蓝色。

```
document.bgColor="lightblue";
```

### 取经代号
1.  页面被称为 `document`，用于在网页中编写脚本。
2.  文档的属性可以通过在 `document` 后面写一个点，然后写属性名来引用。文档对象有许多属性。
3.  在 `<script>` 标记之后，浏览器开始将文本解释为 JavaScript，直到 `</script>` 到来。

## 用 JavaScript 向网页写东西的代码

我们来写 `"Hello World!"` 到一个使用 JavaScript 的空白页。

### 在网页上显示结果

```
<!DOCTYPE html PUBLIC “-//W3C//DTD XHTML 1.0
 Transitional//EN” “http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd”>
 <html xmlns=”http://www.w3.org/1999/xhtml”>
  <head>
    <title></title>
  </head>
  <body>
   <p id="ResultsP"></p>
   <script type="text/javascript">//Script Block 1
   document.getElementById('ResultsP').innerHTML ='Hello World!';
   </script>
  </body>
<html>
```

输出：
![](img/0bee5dca27279b63d04eff3a76cef988.png)

### 取经代号
1.  下面一行已经添加到该代码中。

```
<!DOCTYPE html PUBLIC “-//W3C//DTD XHTML 1.0
 Transitional//EN” “http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd”>
 <html xmlns=”http://www.w3.org/1999/xhtml”>
```

这让网页浏览器知道用户正在使用 XHTML。它实际上对代码没有任何影响；没有额外的线路也能正常工作。

2.  请注意，`<p>` 标签已经使用 `id` 属性被赋予了一个 `id`。

```
<p id=”ResultsP”>
```

这个 `id` 在网页中必须是唯一的，因为它被 JavaScript 用来识别下面一行中的特定 HTML 元素：

```
document.getElementById(‘ResultsP’).innerHTML = ‘Hello World!’;
```

代码的意思很简单：*“给我获取 `id` 为 `ResultsP` 的文档元素，并将该元素内的 HTML 设置为 `Hello World!`”*

重要的是，访问段落的代码在段落之后，否则，代码将试图访问页面中存在的段落之前的段落，并将引发错误。