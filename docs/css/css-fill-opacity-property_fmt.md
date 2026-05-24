# CSS `fill-opacity` 属性

> 原文: [https://www.geeksforgeeks.org/css-fill-opacity-property/](https://www.geeksforgeeks.org/css-fill-opacity-property/)

`fill-opacity` 属性用于设置应用于形状的绘制服务器的不透明度。

## 语法

```html
fill-opacity: [0-1] | <percentage>
```

## 属性值

### 0 到 1 之间的值

用于以十进制值设置填充的不透明度。值 `0` 表示填充完全透明且不可见。值 `1` 表示填充完全不透明且可见。介于两者之间的十进制值将产生半透明填充。

#### 示例

```html
<!DOCTYPE html>
<html>
<head>
  <title>
    CSS | fill-opacity
  </title>
  <style>
    .opacity1 {
      /* completely visible fill */
      fill-opacity: 1.0;
      fill: green;
    }

    .opacity2 {
      fill-opacity: 0.5;
      fill: green;
    }

    .opacity3 {
      fill-opacity: 0.25;
      fill: green;
    }

    .opacity4 {
      /* completely transparent fill */
      fill-opacity: 0;
      fill: green;
    }
  </style>
</head>
<body>
  <h1 style="color: green">
    GeeksforGeeks
  </h1>
  <b>
    CSS | fill-opacity
  </b>
  <div class="container">
    <svg height="250px" width="500px"
      xmlns="http://www.w3.org/2000/svg"
      version="1.1">
      <circle class="opacity1" cx="100"
        cy="100" r="50"/>
      <circle class="opacity2" cx="250"
        cy="100" r="50"/>
      <circle class="opacity3" cx="400"
        cy="100" r="50"/>
      <circle class="opacity4" cx="400"
        cy="100" r="50"/>
    </svg>
  </div>
</body>
</html>
```

#### 输出
![in-values](img/7f747c293de6e261d86302a69c6fb4a5.png)

### 百分比

用于以百分比值设置填充的不透明度。值 `0%` 表示填充完全透明且不可见。值 `100%` 表示填充完全不透明且可见。介于两者之间的百分比值将产生半透明填充。

#### 示例

```html
<!DOCTYPE html>
<html>
<head>
  <title>
    CSS | fill-opacity
  </title>
  <style>
    .opacity1 {
      /* completely visible fill */
      fill-opacity: 100%;
      fill: green;
    }

    .opacity2 {
      fill-opacity: 50%;
      fill: green;
    }

    .opacity3 {
      fill-opacity: 25%;
      fill: green;
    }

    .opacity4 {
      /* completely transparent fill */
      fill-opacity: 0%;
      fill: green;
    }
  </style>
</head>
<body>
  <h1 style="color: green">
    GeeksforGeeks
  </h1>
  <b>
    CSS | fill-opacity
  </b>
  <div class="container">
    <svg height="250px" width="500px"
      xmlns="http://www.w3.org/2000/svg"
      version="1.1">
      <rect class="opacity1" x="25"
         y="10" height="150" width="100"/>
      <rect class="opacity2" x="175"
         y="10" height="150" width="100"/>
      <rect class="opacity3" x="325"
         y="10" height="150" width="100"/>
      <rect class="opacity4" x="325"
         y="10" height="150" width="100"/>
    </svg>
  </div>
</body>
</html>
```

#### 输出
![in-percentage](img/1ce4a0eae7b5ebbd5a20dc2fae59c442.png)

## 支持的浏览器

由 `fill-opacity` 属性支持的浏览器如下：

*   Chrome
*   Firefox
*   Safari
*   Opera
*   Internet Explorer 9