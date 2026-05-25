# HTML DOM 输入日期 stepDown() 方法

> 原文：[https://www.geeksforgeeks.org/html-dom-input-date-stepdown-method/](https://www.geeksforgeeks.org/html-dom-input-date-stepdown-method/)

`stepDown()` 方法用于将日期字段的值递减指定的数字。它只能在日级别使用，不能在月和年级别使用。

## 语法

```html
inputdateObject.stepDown(number)
```

## 使用的参数

*   `number`：用于指定日期字段应减少的天数。

下面的程序说明了 `stepDown` 属性：

## 示例

将日期字段的值递减 2 天。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      Input Date stepDown Property in HTML
  </title>
    <style>
        h1 {
            color: green;
        }

        h2 {
            font-family: Impact;
        }

        body {
            text-align: center;
        }
    </style>
</head>

<body>

<h1>GeeksforGeeks</h1>
    <h2>Input Date stepDown Property
    </h2>
    <br>

<input type="date" 
           id="Test_Date">

<p>To decrease the step, 
      double click the "Decrease Step" button.
  </p>

<button ondblclick="My_Date()">
      Decrease Step
  </button>

<p id="test">
  </p>

<script>
        function My_Date() {
            // Decrease 2 days.
            document.getElementById(
              "Test_Date").stepDown(2);
        }
    </script>

</body>

</html>
```

## 输出

![](img/0aa2c18ebdb48a40e9cf0dc7e2680e0b.png)

点击 ![](img/af2c9a931b9e458668bb054f85f58225.png) 按钮后

## 支持的浏览器

*   苹果 Safari
*   微软 Edge
*   火狐浏览器
*   谷歌 Chrome
*   Opera