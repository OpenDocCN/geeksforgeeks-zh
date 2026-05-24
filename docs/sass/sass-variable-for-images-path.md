# 图像路径的 SASS 变量

> 原文:[https://www . geesforgeks . org/sass-variable-for-images-path/](https://www.geeksforgeeks.org/sass-variable-for-images-path/)

每当我们想给我们的网页添加一个图像时，我们不需要在使用 SASS 时总是写下图像的完整路径。我们可以将 images 文件夹的路径存储在一个变量中。将文件夹的路径添加到变量中总是好的。

**声明变量**
**语法:**

```html
$assetPath :"path";
```

**在图像路径中添加变量**
**语法:**

```html
background: url(#{$assetPath}/gfg.gif);
```

**示例 1:** SASS 文件

```html
$assetPath :"/assets/images";
body {
  margin: 0 auto;
  background: url(#{$assetPath}/gfg.gif);
  width: 100%; 
}
```

**输出:**编译后的 CSS 文件

```html
body {
  margin: 0 auto;
  background: url(/assets/images/gfg.gif);
  width: 100%; 
}
```

我们还可以在图像的单个路径中使用多个变量。

**语法:**

```html
background: url(#{$variable1}/#{$variable2}/#{$variable3});
```

**示例 2:** SASS 文件

```html
$assetsPath :"/assets/images";
$project :"project2";
body {
  margin: 0 auto;
  background: url(#{$assetsPath}/#{$project}/gfg.gif);
  width: 100%; 
}
```

**输出:**编译后的 CSS 文件

```html
body {
  margin: 0 auto;
  background: url(/assets/images/project/gfg.gif);
  width: 100%; 
}
```