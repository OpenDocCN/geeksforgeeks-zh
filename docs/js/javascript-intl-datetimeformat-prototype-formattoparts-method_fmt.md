## JavaScript `Intl.DateTimeFormat.prototype.formatToParts()` 方法

> 原文: [https://www.geeksforgeeks.org/javascript-intl-datetimeformat-prototype-formattoparts-method/](https://www.geeksforgeeks.org/javascript-intl-datetimeformat-prototype-formattoparts-method/)

`Intl.DateTimeFormat.prototype.formatToParts()` 方法是 JavaScript 中的一个内置方法，它允许对 `DateTimeFormat` 格式化程序生成的字符串进行区域设置感知格式化。

### 语法

```javascript
dateTimeFormat.formatToParts( date )
```

### 参数

该方法接受如上所述的单个参数，描述如下：

*   `date`: 为可选参数，保存要格式化的日期。

### 返回值

这个方法返回一个包含格式化日期的数组。

下面的例子说明了 `Intl.DateTimeFormat.prototype.formatToParts()` 方法在 JavaScript 中的使用：

### 示例 1

```javascript
let geeks = {month: 'numeric', day: 'numeric', year: "numeric"};
let result = new Intl.DateTimeFormat("en-u-ca-chinese", geeks);
let datetime = Date.UTC(2012, 11, 17, 3);
let val = result.formatToParts(datetime);
console.log(val[0]);
console.log(val[1]);
console.log(val[2]);
console.log(val[3]);
```