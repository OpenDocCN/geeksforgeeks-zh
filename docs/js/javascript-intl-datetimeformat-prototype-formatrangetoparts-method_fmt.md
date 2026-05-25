# Intl.DateTimeFormat.prototype.formatRangeToParts() 方法

> 原文：[https://www.geeksforgeeks.org/javascript-intl-datetimeformat-prototype-formatrangetoparts-method/](https://www.geeksforgeeks.org/javascript-intl-datetimeformat-prototype-formatrangetoparts-method/)

`Intl.DateTimeFormat.prototype.formatRangeToParts()` 方法是 JavaScript 中的一个内置方法，用于允许区域特定的标记来表示由 `DateTimeFormat` 格式化程序生成的格式化日期范围的每个部分。

**语法：**

```
Intl.DateTimeFormat.prototype.formatRangeToParts(startDate, endDate)
```

**参数：** 该方法接受两个参数，如下所述：

*   `startDate`：此参数所表示范围的开始日期。
*   `endDate`：此参数所表示范围的结束日期。

下面的例子说明了 JavaScript 中的 `Intl.DateTimeFormat.prototype.formatRangeToParts()` 方法：

**例 1：**

### Javascript

```
const startDate = new Date(Date.UTC(1997, 5, 30, 3, 3, 3));
const endDate = new Date(Date.UTC(2073, 7, 6, 11, 0, 0));

let result = new Intl.DateTimeFormat("hi", {
    hour: 'numeric',
    minute: 'numeric'
});

console.log(result.formatRange(startDate, endDate));
let val = result.formatRangeToParts(startDate, endDate);
console.log(val[0]);
console.log(val[2]);
console.log(val[3]);
console.log(val[8]);
```

**输出：**

```
"30/6/1997, 8:33 am – 6/8/2073, 4:30 pm"
Object { type: "day", value: "30", source: "startRange" }
Object { type: "month", value: "6", source: "startRange" }
Object { type: "literal", value: "/", source: "startRange" }
Object { type: "minute", value: "33", source: "startRange" }
```

**例 2：**

### Javascript

```
let geek1 = new Date(Date.UTC(1997, 5, 30, 10, 0, 0));
let geek2 = new Date(Date.UTC(2020, 2, 26, 11, 0, 0));
let geek3 = new Date(Date.UTC(2073, 6, 23, 10, 0, 0));

let result1 = new Intl.DateTimeFormat("en", {
    year: '2-digit',
    month: 'numeric',
    day: 'numeric',
    hour: 'numeric',
    minute: 'numeric'
});
console.log(result1.format(geek1));
console.log(result1.formatRange(geek1, geek2));
console.log(result1.formatRange(geek1, geek3));

let result2 = new Intl.DateTimeFormat("hi", {
    year: 'numeric',
    month: 'short',
    day: 'numeric'
});
console.log(result2.format(geek1));
console.log(result2.formatRange(geek1, geek2));
console.log(result2.formatRange(geek1, geek3));
```

**输出：**

```
"month" "6" "startRange"
"literal" "/" "startRange"
"day" "30" "startRange"
"literal" "/" "startRange"
"year" "1997" "startRange"
"literal" ", " "startRange"
"hour" "8" "startRange"
"literal" ":" "startRange"
"minute" "33" "startRange"
"literal" " " "startRange"
"dayPeriod" "AM" "startRange"
"literal" " – " "shared"
"month" "8" "endRange"
"literal" "/" "endRange"
"day" "6" "endRange"
"literal" "/" "endRange"
"year" "2073" "endRange"
"literal" ", " "endRange"
"hour" "4" "endRange"
"literal" ":" "endRange"
"minute" "30" "endRange"
"literal" " " "endRange"
"dayPeriod" "PM" "endRange"
```

**支持的浏览器：** 支持 `Intl.DateTimeFormat.prototype.formatRangeToParts()` 方法的浏览器如下：

*   WebView Android 76 及以上
*   Chrome 76 及以上
*   Opera Android 54 及以上
*   Edge 79 及以上
*   Firefox 91 及以上