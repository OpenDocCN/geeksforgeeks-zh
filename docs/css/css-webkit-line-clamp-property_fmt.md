# CSS -webkit-line-clamp 属性

> 原文：[https://www.geeksforgeeks.org/css-webkit-line-clamp-property/](https://www.geeksforgeeks.org/css-webkit-line-clamp-property/)

`-webkit-line-clamp` 属性用于限制块容器可能包含的行数。仅当 `display` 属性设置为 `-webkit-box` 或 `-webkit-inline-box` 且 `-webkit-box-orient` 属性设置为 `vertical` 时，此属性才有效。

**语法：**

```html
-webkit-line-clamp: none | integer | initial | inherit
```

**属性值：**

### `none`
用于指定内容不会被截断。这是默认值。

**示例：**

```html
<!DOCTYPE html>
<html>
<head>
  <title>
    -webkit-line-clamp property
  </title>
  <style>
    /* Clipped text for comparison */
    .content-1 {
      width: 300px;
      display: -webkit-box;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: 2;
      overflow: hidden;
    }

    .content-2 {
      width: 300px;
      display: -webkit-box;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: none;
      overflow: hidden;
    }
  </style>
</head>
<body>
  <h1 style="color: green;">
    GeeksforGeeks
  </h1>
  <b>
    -webkit-line-clamp: 2
  </b>
  <p class="content-1">
    GeeksforGeeks is a computer science portal with a huge variety of well written and explained computer science and programming articles, quizzes and interview questions.
  </p>
  <b>-webkit-line-clamp: none</b>
  <p class="content-2">
    GeeksforGeeks is a computer science portal with a huge variety of well written and explained computer science and programming articles, quizzes and interview questions.
  </p>
</body>
</html>
```

**输出：**
![none](img/a4d84ea15db1219b72be40654eb1823b.png)

### `integer`
用于指定内容在多少行后被截断。此值应大于 0。

**示例：**

```html
<!DOCTYPE html>
<html>
<head>
  <title>
    -webkit-line-clamp
  </title>
  <style>
    .content-1 {
      width: 300px;
      display: -webkit-box;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: 1;
      overflow: hidden;
    }

    .content-2 {
      width: 300px;
      display: -webkit-box;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: 3;
      overflow: hidden;
    }
  </style>
</head>
<body>
  <h1 style="color: green;">
    GeeksforGeeks
  </h1>
  <b>
    -webkit-line-clamp: 1
  </b>
  <p class="content-1">
    GeeksforGeeks is a computer science portal with a huge variety of well written and explained computer science and programming articles, quizzes and interview questions.
  </p>
  <b>-webkit-line-clamp: 3</b>
  <p class="content-2">
    GeeksforGeeks is a computer science portal with a huge variety of well written and explained computer science and programming articles, quizzes and interview questions.
  </p>
</body>
</html>
```

**输出：**
![lines](img/bcd964d02734a0de877c2513c6b1f4c6.png)

### `initial`
用于将属性设置为其默认值。

**示例：**

```html
<!DOCTYPE html>
<html>
<head>
  <title>
    -webkit-line-clamp
  </title>
  <style>
    /* Clipped text for comparison */
    .content-1 {
      width: 300px;
      display: -webkit-box;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: 2;
      overflow: hidden;
    }

    .content-2 {
      width: 300px;
      display: -webkit-box;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: initial;
      overflow: hidden;
    }
  </style>
</head>
<body>
  <h1 style="color: green;">
    GeeksforGeeks
  </h1>
  <b>-webkit-line-clamp: 2</b>
  <p class="content-1">
    GeeksforGeeks is a computer science portal with a huge variety of well written and explained computer science and programming articles, quizzes and interview questions.
  </p>
  <b>-webkit-line-clamp: initial</b>
  <p class="content-2">
    GeeksforGeeks is a computer science portal with a huge variety of well written and explained computer science and programming articles, quizzes and interview questions.
  </p>
</body>
</html>
```

**输出：**
![initial](img/43d21207bf2a898678082721b7993728.png)

### `inherit`
用于从其父级继承属性。

**支持的浏览器：**
`-webkit-line-clamp` 属性支持的浏览器如下：

*   Google Chrome
*   Firefox
*   Safari
*   Opera