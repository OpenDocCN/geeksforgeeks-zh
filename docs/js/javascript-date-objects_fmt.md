# JavaScript 日期对象

> 原文：[https://www.geeksforgeeks.org/javascript-date-objects/](https://www.geeksforgeeks.org/javascript-date-objects/)

`Date`对象是 JavaScript 语言的一种内置数据类型，用来和日期和时间一起工作。使用`new`关键字创建日期对象，即`new Date()`。日期对象可以使用 1970 年 1 月 1 日前后 1 亿天内毫秒精度的日期和时间。但是使用另一种方法，我们只能使用本地或世界协调时或格林尼治时间来获取和设置年、月、日、小时、分钟、秒和毫秒字段。所以我们可以用`Date`对象来表示 275755 年之前的日期和时间。

有四种不同的方式来声明日期，基本的事情是日期对象是由`new Date()`操作符创建的。

## 语法

```
new Date()
new Date(milliseconds)
new Date(dataString)
new Date(year, month, date, hour, minute, second, millisecond)
```

## 示例

### new Date()

**参数：** `Date()`构造函数创建一个`Date`对象，该对象根据浏览器的时区设置当前日期和时间。它不接受任何值。

**示例：**

```
<script>
// "geeks" is Date object
var geeks = new Date();

document.write(geeks);
// Prints todays date
</script>
```

**输出：** 我会返回当前的日月日年标准时间。

```
Wed Jul 03 2019 19:01:35 GMT+0530 (India Standard Time)
```

### new Date(milliseconds)

**参数：** 此方法接受单个参数`milliseconds`，它表示任何数值。此参数被视为日期的内部毫秒数表示。

**示例：**

```
<script>
// "geeks" is Date object
var geeks = new Date(4500);

document.write("Todays date : " + geeks);
</script>
```

**输出：**

```
Todays date : Thu Jan 01 1970 05:30:04 GMT+0530 (India Standard Time)
```

### new Date(datastring)

**参数：** 此方法接受单个参数`dataString`，它表示任何字符串值。它是日期的字符串表示形式，并返回包含星期几的数据字符串。

**示例：**

```
<script>
// "geeks" is Date object
var geeks = new Date("October 13, 2013 11:13:00");

document.write("Datastring with day : " + geeks);
</script>
```

**输出：**

```
Datastring with day : Sun Oct 13 2013 11:13:00 GMT+0530 (India Standard Time)
```

### new Date(year, month, date, hour, minute, second, millisecond)

**参数：** 此方法接受七个参数，如下所述：
*   **年：** 代表年的整数值。这应始终指定完整的年份，即使用 2018 年，而不是使用 18 年。
*   **月：** 整数代表月份的值。整数值是从 1 月的 0 开始到 12 月的 11。
*   **日期：** 代表日期的整数值。
*   **小时：** 整数值，表示 24 小时制中的小时。
*   **分钟：** 代表分钟的整数值。
*   **秒：** 整数代表秒的值。
*   **毫秒：** 整数代表毫秒的值。

**示例：**

```
<script>
// "geeks" is Date object
var geeks = new Date(2014, 10, 24, 10, 33, 30, 0);

document.write(geeks);
</script>
```

**输出：**

```
Mon Nov 24 2014 10:33:30 GMT+0530 (India Standard Time)
```

## 日期对象的属性

*   **Prototype：** `Prototype`允许我们给一个对象添加属性和方法。
    *   **日期构造器：** 它定义了创建日期对象原型的函数。

## Date 对象的一些方法

这里有一些定义`Date`对象用法的方法，这些都是非静态的方法。

### 以下方法是根据当地时间返回所有值

| 方法 | 描述 |
| :--- | :--- |
| `Date()` | 它返回当天的日期和时间。 |
| `getDate()` | 它返回指定日期的日期。 |
| `getDay()` | 它返回指定日期的星期几。 |
| `getFullYear()` | 它返回指定日期的年份。 |
| `getYear()` | 此方法返回指定日期的年份。 |
| `getHours()` | 它返回指定日期的小时。 |
| `getMilliseconds()` | 它返回指定日期的毫秒数。 |
| `getMinutes()` | 它返回指定日期的分钟数。 |
| `getMonth()` | 它返回指定日期中的月份。这也找月了。 |
| `getSeconds()` | 此方法返回指定日期的秒数。 |
| `getTime()` | 此方法以毫秒为单位以数值形式返回日期。 |
| `setDate()` | 此方法为指定日期设置一个月中的某一天。 |
| `setFullYear()` | 此方法为指定日期设置整年。 |

还有很多方法。

### 以下方法是根据世界时返回所有值

| 方法 | 描述 |
| :--- | :--- |
| `getUTCDate()` | 它返回指定日期的月份。 |
| `getUTCDay()` | 它返回指定日期的星期几。 |
| `getUTCFullYear()` | 此方法返回指定日期的年份。 |
| `getUTCHours()` | 它返回指定日期的小时数。 |
| `getUTCMilliseconds()` | 此方法返回指定日期的毫秒形式。 |
| `getUTCMinutes()` | 此方法返回指定日期的分钟数。 |
| `getUTCMonth()` | 此方法返回指定日期的月份。 |