# JavaScript Date setUTCMonth()方法

> 原文: [https://www.geeksforgeeks.org/javascript-date-setutcmonth-method/](https://www.geeksforgeeks.org/javascript-date-setutcmonth-method/)

下面是 `Date.setUTCMonth()` 方法的例子。

## 示例

### JavaScript

```javascript
// Here a date has been assigned according to
// universal time while creating Date object
var dateobj = new Date('October 13, 1996 05:35:32 GMT-3:00');

// New month of January is being set in above Date
// Object with the help of setUTCMonth() method
dateobj.setUTCMonth(0);

// New month from above Date Object is
// being extracted using getUTCMonth()
var B = dateobj.getMonth();

// Printing new month
document.write(B);
```

**输出:**

```
0
```

`date.setUTCMonth()` 方法用于将根据世界时的月份设置使用 `Date()` 构造函数创建的日期对象。

## 语法

```
dateObj.setUTCMonth(monthValue);
```

## 参数

该方法接受如上所述的单个参数，如下所述:

*   **monthValue**: 此参数保存月的值，用于在 `Date()` 构造函数中设置。

## 返回值

返回 `setUTCMonth()` 方法设置的新的即更新的月份。

## 注意

`dateObj` 是使用 `Date()` 构造函数创建的有效日期对象，我们要在其中设置月份。

上述方法的更多代码如下:

### 程序 1

如果在 `Date()` 构造函数中我们没有给出任何月份，那么 `setUTCMonth()` 方法仍然会设置一个新的月份作为它的参数。

```javascript
// Here month has not been assigned according to
// universal time while creating Date object
var dateobj = new Date('1996, 05:35:32 GMT-3:00');

// New month of 2 is being set in above Date
// Object with the help of setUTCMonth() method
dateobj.setUTCMonth(2);

// New month from above Date Object is
// being extracted using getUTCMonth()
var B = dateobj.getUTCMonth();

// Printing new month
document.write(B);
```

**输出:**

```
2
```

### 程序 2

如果 `Date()` 构造函数中没有给定任何参数，则 `setUTCMonth()` 方法仍然根据世界时将年、月、日等设置为当前日期。

这里 11 是 12 月的新月份，1 是当前日期，根据世界时，2018 是当前年份。

```javascript
// Here nothing has been assigned according to
// universal time while creating Date object
var dateobj = new Date();

// New month of 11 is being set in above Date
// Object with the help of setUTCMonth() method
dateobj.setUTCMonth(11);

// Month from above Date Object is
// being extracted using getUTCMonth()
var B = dateobj.getUTCMonth();

// Date from above Date Object is
// being extracted using getUTCDate()
var C = dateobj.getUTCDate();

// Year from above Date Object is
// being extracted using getUTCFullYear()
var D = dateobj.getUTCFullYear();

// Printing new month
document.write(B + '<br />');

// Printing current date
document.write(C + '<br />');

// Printing current year
document.write(D + '<br />');
```

**输出:**

```
11
1
2018
```

### 程序 3

如果给定第 15 个月的值作为 `setUTCMonth()` 方法的参数，它将设置 3 为月份，因为月份范围从 0 到 11，因此 `15 - 12 = 3`，这里减去 12，因为 0 到 11 是 12。

这里 3 是 4 月的新月份，从 1996 年开始年份变成 1997 年，因为月份范围是从 0 到 11，也就是总共 12 个，我们把新月份设置为 3，从 1996 年开始年份增加 1 到 1997 年，月份根据世界时变成 3。

```javascript
// Here date has been assigned according to
// universal time while creating Date object
var dateobj = new Date('October 13, 1996 05:35:32 GMT-3:00');

// New month of 15 is being set in above Date
// Object with the help of setUTCMonth() method
dateobj.setUTCMonth(15);

// Month from above Date Object is
// being extracted using getUTCMonth()
var B = dateobj.getUTCMonth();

// Year from above Date Object is
// being extracted using getUTCFullYear()
var C = dateobj.getUTCFullYear();

// Printing new month
document.write(B + '<br />');

// Printing new year
document.write(C);
```

**输出:**

```
3
1997
```

## 支持的浏览器

JavaScript Date `setUTCMonth()` 方法支持的浏览器如下:

*   谷歌 Chrome 1 及以上版本
*   Edge 12 及以上
*   Firefox 1 及以上版本
*   Internet Explorer 4 及以上版本
*   Opera 4 及以上
*   Safari 1 及以上