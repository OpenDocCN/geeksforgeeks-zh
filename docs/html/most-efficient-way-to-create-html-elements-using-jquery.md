# 使用 jQuery 创建 HTML 元素的最有效方法

> 原文:[https://www . geeksforgeeks . org/最有效的创建 html 元素的方法-使用-jquery/](https://www.geeksforgeeks.org/most-efficient-way-to-create-html-elements-using-jquery/)

在本文中，我们将研究 4 种可用于创建 HTML 元素的 [jQuery](https://www.geeksforgeeks.org/jquery-tutorials/) 技术，我们将通过不同的方法测试创建元素的代码。

**方法:**一个比较简单的方法是只使用*$('<div></div>')*这对于可读性来说是很棒的但是从技术上来说这段代码会创建一个 *< div >* 元素，但是它不会将其添加到你的 HTML DOM 中。您需要使用一些其他方法，如 [*【追加】)*](https://www.geeksforgeeks.org/jquery-append-method/) *、* [*前置()*](https://www.geeksforgeeks.org/jquery-prepend-with-examples/) 等。

建议运行并测试下面的代码，并检查创建元素的最快技术，因为代码所花费的时间因网络浏览器而异。

对于下面的代码，您必须将 jQuery 合并到代码中。最简单的方法之一是将 jQuery CDN 复制并粘贴到您的 HTML 标题标签中。

**使用的 CDN 链接:**

```html
https://code.jquery.com/jquery-3.5.1.min.js
```

**方法 1:** 在下面的例子中，[**document . createelement()**](https://www.geeksforgeeks.org/html-dom-createelement-method/)方法创建了 HTML*【div】*元素节点。[**date . gettime()**](https://www.geeksforgeeks.org/javascript-date-gettime-method/)**方法用于返回自 1970 年 1 月 1 日以来的毫秒数。运行下面的代码来了解它的性能。**

****语法:****

```html
$((document.createElement('div')));
```

## **HTML**

```html
<!DOCTYPE html>
<html>
<head>

  <!-- Embedding jQuery using jQuery CDN -->
  <script src=
"https://code.jquery.com/jquery-3.5.1.min.js"
          integrity=
"sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" 
          crossorigin="anonymous">
  </script>
</head>
<body>
  <script>
    // returns time in milliseconds
    var start = new Date().getTime(); 

        for (i = 0; i < 1000000; ++i) {            
            var e = $((document.createElement('div'))); 
        }

        var end = new Date().getTime();
        alert(end - start);       
  </script>
</body>
</html>
```

****输出:****

```html
875
```

****方法二:****

****语法:****

```html
$(('<div>'));
```

## **HTML**

```html
<!DOCTYPE html>
<html>
<head>
  <!-- Embedding jQuery using jQuery CDN -->
  <script src=
"https://code.jquery.com/jquery-3.5.1.min.js" 
          integrity=
"sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0="
          crossorigin="anonymous">
  </script>
</head>
<body>
  <script>
    // returns time in milliseconds
    var start = new Date().getTime(); 

        for (i = 0; i < 1000000; ++i) {
            var e = $(('<div>'));     
        }

        var end = new Date().getTime();
        alert(end - start);       
  </script>
</body>
</html>
```

****输出:****

```html
1538
```

****方法 3:****

****语法:****

```html
$(('<div></div>'));
```

## **HTML**

```html
<!DOCTYPE html>
<html>
<head>

  <!-- Embedding jQuery using jQuery CDN -->
  <script src=
"https://code.jquery.com/jquery-3.5.1.min.js" 
          integrity=
"sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" 
          crossorigin="anonymous"></script>
</head>
<body>
  <script>
    // returns time in milliseconds
    var start = new Date().getTime();

        for (i = 0; i < 1000000; ++i) {
            var e = $(('<div></div>')); 
        }

        var end = new Date().getTime();
        alert(end - start);       
  </script>
</body>
</html>
```

****输出:****

```html
2097
```

****方法 4:****

****语法:****

```html
$(('<div/>'));
```

## **HTML**

```html
<!DOCTYPE html>
<html>
<head>

  <!-- Embedding jQuery using jQuery CDN -->
  <script src=
"https://code.jquery.com/jquery-3.5.1.min.js"
          integrity=
"sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0="
     crossorigin="anonymous">
  </script>
</head>
<body>
  <script>
   // returns time in milliseconds
    var start = new Date().getTime(); 

        for (i = 0; i < 1000000; ++i) {
            var e = $(('<div/>'));
        }

        var end = new Date().getTime();
        alert(end - start);       
  </script>
</body>
</html>
```

****输出:****

```html
2037
```

**为了更好地理解，尝试在 JavaScript 引擎上运行基准测试。**

****结论**:[$(document . createelement(' div ')；](https://www.geeksforgeeks.org/html-dom-createelement-method/)是最快的方法，即使是基准测试也支持，这是使用 jQuery 创建 HTML 元素最快的技术。**

****原因:**是因为 jQuery 不需要把它识别为一个元素，自己创建元素。**

****替代方式**:只使用**document . createelement(' div ')**不使用 jQuery 会大大提高效率，还会自动将元素追加到 DOM 中。**