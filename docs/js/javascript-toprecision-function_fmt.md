# JavaScript Number toPrecision()方法

> 原文: [https://www.geeksforgeeks.org/javascript-toprecision-function/](https://www.geeksforgeeks.org/javascript-toprecision-function/)

下面是 `Number.toPrecision()` 方法的示例。

## 示例

```javascript
<script type="text/javascript">
    var num = 213.45689;
    document.write(num.toPrecision(3));
</script>
```

输出:

```
213
```

## 描述

JavaScript 中的 `toPrecision()` 方法用于将数字格式化为特定的精度或长度。如果格式化的数字需要比原始数字更多的数字，则还会添加小数和零来创建指定的长度。

## 语法

```javascript
number.toPrecision(value)
```

`toPrecision()` 方法与一个数字一起使用，如上面使用 `.` 的语法所示操作符。此方法将数字格式化为指定的长度。

## 参数

该方法接受单个参数 `value`。此参数也是可选的，它表示用户在格式化数字中想要的有效位数的值。

## 返回值

JavaScript 中的 `toPrecision()` 方法返回一个字符串，该字符串中的数字被格式化为指定的精度。

## 示例说明

下面是一些例子来说明 `toPrecision()` 方法：

### 1. 在 toPrecision() 方法中不传递参数

如果在 `toPrecision()` 方法中不传递参数，则格式化后的数字将与输入数字完全相同。不过，它将被表示为字符串而不是数字。

**代码示例 1:**

```javascript
<script type="text/javascript">
    var num = 213.45689;
    document.write(num.toPrecision());
</script>
```

输出:

```
213.45689
```

### 2. 在 toPrecision() 方法中传递一个参数

如果传递给 `toPrecision()` 方法的精度长度小于原始数字的长度，则数字将四舍五入到该精度。

**代码示例 2:**

```javascript
<script type="text/javascript">
    var num = 213.45689;
    document.write(num.toPrecision(4));
</script>
```

输出:

```
213.5
```

### 3. 传递一个导致输出中添加零的参数

如果传递给 `toPrecision()` 方法的精度长度大于原始数字的长度，则会在输入数字后添加零以满足指定的精度。

**代码示例 3:**

```javascript
<script type="text/javascript">
    var num = 213.45689;
    document.write(num.toPrecision(12));

    var num2 = 123;
    document.write(num2.toPrecision(5));
</script>
```

输出:

```
213.456890000
123.00
```

## 注意

如果指定的精度不在 1 到 100（包括 1 和 100）之间，将导致范围错误。

## 支持的浏览器

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧