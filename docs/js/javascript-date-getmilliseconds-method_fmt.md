# JavaScript Date.getMilliseconds() 方法

> 原文：[https://www.geeksforgeeks.org/javascript-date-getmilliseconds-method/](https://www.geeksforgeeks.org/javascript-date-getmilliseconds-method/)

下面是 `Date.getMilliseconds()` 方法的例子。

## 示例

### JavaScript

```javascript
// Here a date has been assigned
// while creating Date object
var DateObj = new Date('October 15, 1996 05:35:32:77');

// millisecond from above date object is
// being extracted using getMilliseconds().
var millisec = DateObj.getMilliseconds();

// Printing millisecond
document.write(millisec);
```

**输出：**

```
77
```

`Date.getMilliseconds()` 方法用于从给定的 `Date` 对象中获取毫秒。

**语法：**

```javascript
DateObj.getMilliseconds()
```

**参数：** 本功能不接受任何参数。

**返回值：** 返回给定日期对象的毫秒数。毫秒是介于 0 到 999 之间的整数值。

上述方法的更多代码如下：

### 程序 1

月份的日期必须在 1 到 31 之间，因为没有一个月份的日期大于 31，这就是为什么它返回 `NaN`，即不是一个数字，因为月份的日期不存在。

```javascript
// Here a date has been assigned
// while creating Date object
var DateObj = new Date('October 33, 1996 05:35:32:77');

// millisecond from above dateobject is
// being extracted using getMilliseconds().
var millisec = DateObj.getMilliseconds();

// Printing millisecond
document.write(millisec);
```

**输出：**

```
NaN
```

### 程序 2

如果没有给出毫秒，则返回零(0)。

```javascript
// Here a date has been assigned
// while creating Date object
var DateObj = new Date('October 13, 1996 05:35:32');

// millisecond from above dateobject is being
// extracted using getMilliseconds()
var millisec = DateObj.getMilliseconds();

// Printing millisecond
document.write(millisec);
```

**输出：**

```
0
```

### 示例 3

如果没有给 `Date()` 构造函数任何参数，则返回当前毫秒。

```javascript
// Creating a Date Object
var DateObj = new Date();

// millisecond from above Date object is being
// extracted using getMilliSeconds()
var millisec = DateObj.getMilliseconds();

// Printing current millisecond
document.write(millisec);
```

**输出：**

```
（当前毫秒数）
```

### 示例 4

如果在创建 `Date` 对象时给定毫秒为 1003，函数将返回 0 作为异常，因为毫秒范围在 0 到 999 之间，1003 超出了该范围。

```javascript
// Here a date has been assigned
// while creating Date object
var DateObj = new Date('October 13, 1996 05:35:32:1003');

// millisecond from above dateobject is being
// extracted using getMilliseconds()
var millisec = DateObj.getMilliseconds();

// Printing millisecond
document.write(millisec);
```

**输出：**

```
0
```

**支持的浏览器：** 下面列出了 `JavaScript Date.getMilliseconds()` 方法支持的浏览器：

*   Google Chrome 1 及以上版本
*   Edge 12 及以上
*   Firefox 1 及以上版本
*   Internet Explorer 4 及以上版本
*   Opera 4 及以上
*   Safari 1 及以上