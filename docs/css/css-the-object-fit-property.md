# CSS 对象适配属性

> 原文:[https://www.geeksforgeeks.org/css-the-object-fit-property/](https://www.geeksforgeeks.org/css-the-object-fit-property/)

CSS **对象适配属性**用于指定应该如何调整图像或视频的大小以适合其内容框。该属性指定了填充内容框或容器内内容的各种方式，如保持长宽比或向上拉伸&以尽可能提升空间等。被替换元素的内容对象在元素框中的对齐位置可以通过[对象位置](https://www.geeksforgeeks.org/css-object-position-property/)属性来更改。

**语法:**

```html
object-fit: fill|contain|cover|scale-down|none|initial|inherit;
```

**属性值:**下面的例子很好地描述了所有的属性。

**填充:**为默认值。被替换的图像被拉伸以适合内容框。被替换的图像将完全填满盒子，而不考虑它的长宽比。

**语法:**

```html
object-fit: fill;
```

**示例:**本示例说明了**对象拟合**属性的使用，该属性的值设置为填充。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | The object-fit Property </title>
    <style>
    img {
        width: 200px;
        height: 400px;
        object-fit: Fill;
    }
    </style>
</head>

<body>
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png"
          alt="GeeksforGeeks"
          width="667"
          height="184">
</body>
</html>
```

**输出:**

![](img/6435ac335a172bbcf298775210903154.png)

**包含:**替换的图像保留了原始图像的纵横比，同时适合内容框。

**语法:**

```html
object-fit: contain;
```

**示例:**该示例说明了**对象拟合**属性的使用，该属性的值被设置为包含。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | The object-fit Property </title>
    <style>
    img {
        width: 200px;
        height: 400px;
        object-fit: contain;
    }
    </style>
</head>

<body>
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png"
         alt="GeeksforGeeks"
         width="667"
         height="184">
</body>
</html>
```

**输出:**

![](img/6d3f1d6efb805b5a73c1409237e07257.png)

**封面:**该值还保留了原图像是替换图像时在内容框中的长宽比。有时，当原始图像的纵横比与内容框的纵横比不匹配时，会对其进行剪裁以适合。

**语法:**

```html
object-fit: cover;
```

**示例:**该示例说明了**对象拟合**属性的使用，该属性的值被设置为覆盖。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | The object-fit Property </title>
    <style>
    img {
        width: 200px;
        height: 400px;
        object-fit: cover;
    }
    </style>
</head>

<body>
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png"
          alt="GeeksforGeeks"
          width="667"
         height="184">
</body>
</html>
```

**输出:**

![](img/c523df0916ef91113bfcae58f276e7e5.png)

**无:**替换后的图像会忽略原图像的长宽比。因此，它不会调整大小。

**语法:**

```html
object-fit: none;
```

**示例:**本示例说明了**对象拟合**属性的使用，该属性的值设置为无。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | The object-fit Property </title>
    <style>
    img {
        width: 200px;
        height: 400px;
        object-fit: none;
    }
    </style>
</head>

<body>
  <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png"
       alt="GeeksforGeeks"
       width="667"
       height="184">
</body>
</html>
```

**输出:**

![](img/ea6b56d0cc4120aa8a851b7f6b0576b4.png)

**缩小:**被替换的图像被重新调整大小，就像没有指定或指定了包含一样，并导致最小的对象大小。

**语法:**

```html
object-fit: scale-down;
```

**示例:**本示例说明了**对象拟合**属性的使用，该属性的值设置为缩小。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | The object-fit Property </title>
    <style>
    img {
        width: 200px;
        height: 200px;
        object-fit: scale-down;
    }
    </style>
</head>

<body>
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png"
         alt="GeeksforGeeks"
         width="667"
         height="184">
</body>
</html>
```

**输出:**

![](img/b5cdf5896811c658178bdfd416ebeae2.png)

**初始值:**用于设置默认值，即当默认值被填充时，替换的图像被拉伸以适合内容框。

**语法:**

```html
object-fit: initial;
```

**示例:**本示例说明了**对象拟合**属性的使用，该属性的值设置为初始值。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | The object-fit Property </title>
    <style>
    img {
        width: 200px;
        height: 400px;
        object-fit: initial;
    }
    </style>
</head>

<body>
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png"
         alt="GeeksforGeeks"
         width="667"
         height="184">
</body>
</html>
```

**输出:**

![](img/13469449baaa5f26c4df4b648a4c5327.png)

**inherit:** Inherit 从父元素接收属性。当它与根元素一起使用时，将使用初始属性。

**语法:**

```html
object-fit: inherit;
```

**示例:**该示例说明了**对象拟合**属性的使用，该属性的值被设置为继承。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | The object-fit Property </title>
    <style>
    .object {
        object-fit: none;
    }

    img {
        width: 200px;
        height: 400px;
        object-fit: inherit;
    }
    </style>
</head>

<body>
    <div class="object">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png"
             alt="GeeksforGeeks"
             width="667"
             height="184">
    </div>
    <!--Here img inherits property from parent i.e none from class object-->

</body>
</html>
```

**输出:**

![](img/70a1564743d606fcc6db937dc166a48d.png)

**支持的浏览器:**对象适配属性支持的浏览器如下:

*   谷歌 Chrome 32.0
*   Firefox 36.0
*   微软边缘 79.0
*   Opera 19.0
*   Safari 10.0