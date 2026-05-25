# JavaScript Date toLocaleDateString() 方法

> 原文: [https://www.geeksforgeeks.org/javascript-date-tolocaledatestring-method/](https://www.geeksforgeeks.org/javascript-date-tolocaledatestring-method/)

下面是 `Date toLocaleDateString()` 方法的例子。

### 例:

```javascript
<script>
    var dateObj = new Date();
    var options = { weekday: "long",
                    year: "numeric",
                    month: "short",
                    day: "numeric" };
    document.write(dateObj.toLocaleDateString("en-US"));
    document.write("<br>");
    document.write(dateObj.toLocaleDateString("en-US", options));
</script>
```

### 输出:

```
6/24/2018
Sunday, Jun 24, 2018
```

`dateObj.toLocaleDateString()` 方法用于将日期转换为字符串。

## 语法:

```
dateObj.toLocaleDateString([locales][, options])
```

## 参数:

该方法接受两个参数，如下所述：

*   `locales`: 此参数是包含一个或多个语言或地区标记的地区字符串数组。请注意，它是一个可选参数。如果您想在应用程序中使用特定的语言格式，请在 `locales` 参数中指定该语言。
*   `options`: 也是可选参数，包含指定比较选项的属性。有些属性是 `localeMatcher`、`timeZone`、`weekday`、`year`、`month`、`day`、`hour`、`minute`、`second` 等。

## 返回值:

它以由区域设置指定的特定格式的字符串值返回日期。

## 注意:

`Date` 对象应该是有效的日期对象。

以上方法的更多代码如下:

### 程序 1:

没有参数这个方法的返回值在脚本中不能依赖。它使用操作系统的区域设置惯例。

```javascript
<script>
   var dateObj = new Date(1993, 6, 28, 14, 39, 7);
   document.write(dateObj.toLocaleDateString());
</script>
```

### 输出:

```
7/28/1993
```

### 注意:

并非所有浏览器都支持 `locales` 和 `options` 参数。要检查是否支持，我们可以使用以下功能:

```javascript
function toLocaleDateStringSupportsLocales() {
    try {
        new Date().toLocaleDateString('i');
    }
    catch (e) {
        return e.name === 'RangeError';
    }
    return false;
}
```

## 支持的浏览器:

`JavaScript Date toLocaleDateString()` 方法支持的浏览器如下:

*   谷歌 Chrome 1 及以上版本
*   Edge 12 及以上
*   Firefox 1 及以上版本
*   Internet Explorer 5.5 及以上版本
*   Opera 5 及以上
*   Safari 1 及以上