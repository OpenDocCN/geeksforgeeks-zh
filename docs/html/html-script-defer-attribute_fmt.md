
# HTML `<script>` 延迟属性

> &amp;# x539F；&amp;# x6587；&amp;# xFF1A；[HTML `<script>` 延迟属性](https://www.geeksforgeeks.org/html-script-delay-attribute/)

HTML `defer` 属性是一个布尔属性，用于指定在页面解析完毕时执行脚本。此属性仅适用于外部脚本。

## 句法

```html
<script defer>
  // 脚本代码
</script>
```

## 示例

```html
<!DOCTYPE html>
<html>
<head>
  <title>HTML `<script>` 延迟属性</title>
</head>
<body>
  <h1 style="color:green;">geesforgeeks</h1>
  <h2>HTML `<script>` 延迟属性</h2>
  <script id="myGeeks" type="text/JavaScript" src="my_script.js" defer>
  </script>
  <br>
  <button type="button" onclick="myFunction()">提交</button>
</body>
</html>
```

## 外部脚本

```javascript
function myFunction() {
  alert("脚本执行");
}
```

## 输出

### 点击前

![点击前](img/脚本延期属性.png)

### 支持的浏览器

- Google Chrome
- Internet Explorer
- Firefox
- Apple Safari
</root>
