# JavaScript Date getUTCMinutes() 方法

> 原文：[https://www.geeksforgeeks.org/javascript-date-getutcminutes-method/](https://www.geeksforgeeks.org/javascript-date-getutcminutes-method/)

下面是 `Date.getUTCMinutes()` 方法的例子。

## 示例

### 示例 1

```html
<script>
   // Here a date has been assigned according
   // to universal time while creating Date object
   var dateObj =
   new Date('October 15, 1996 23:35:32 GMT+11:00');

   // Minute from above date object is
   // being extracted using getUTCMinutes().
   var B = dateObj.getUTCMinutes();

   // Printing minute according to universal time
   document.write(B);
</script>
```

**输出：**

```
35
```

`dateObj.getUTCMinutes()` 方法用于根据通用时间从给定的 `Date` 对象中获取分钟。

## 语法

```
dateObj.getUTCMinutes();
```

## 参数

此方法不接受任何参数。它只是和一个日期对象一起使用，我们想从中获取分钟数。

## 返回值

根据世界时返回给定日期的分钟数。分钟是一个从 0 到 59 的整数值。

## 注意

在上面的语法中，`dateObj` 是使用 `Date()` 构造函数创建的有效日期对象，我们希望从中获取分钟。

上述方法的更多代码如下：

### 示例 2

月份的日期应该在 1 到 31 之间，因为没有一个月份的日期大于 31，这就是为什么它返回 `NaN`，即不是数字，因为月份的日期不存在。如果月份日期不存在，根据世界时，分钟将不存在。

```html
<script>
   // Here a date has been assigned according
   // to universal time while creating Date object.
   var dateObj =
   new Date('October 33, 1996 23:35:32 GMT+11:00');

   // Minute from above data object is
   // being extracted using getUTCMinutes().
   var B = dateObj.getUTCMinutes();

   // Printing minute according to universal time.
   document.write(B);
</script>
```

**输出：**

```
NaN
```

### 示例 3

如果在创建 `Date` 对象时没有给 `Date()` 构造函数分钟，那么 `getUTCMinutes()` 方法根据世界时返回零（0）。这是个例外。

```html
<script>
    // Here a date has been assigned according
    // to universal time while creating Date object.
    var dateObj =
    new Date('October 13, 1996 GMT+11:00');

    // Minute from above data object is
    // being extracted using getUTCMinutes().
    var B = dateObj.getUTCMinutes();

    // Printing minute according to
    // universal time.
    document.write(B);
</script>
```

**输出：**

```
0
```

### 示例 4

如果在创建 `Date` 对象时没有给 `Date()` 构造函数任何作为参数的内容，`getUTCMinutes()` 方法将根据世界时返回当前分钟数。

```html
<script>
   // Here nothing has been assigned according
   // to universal time while creating Date object.
   var dateObj = new Date();

   // Minute from above data object is
   // being extracted using getUTCMinutes().
   var B = dateObj.getUTCMinutes();

   // Printing current minute
   // according to universal time.
   document.write(B);
</script>
```

**输出：**

```
(当前分钟数，例如 42)
```

## 支持的浏览器

JavaScript Date `getUTCMinutes()` 方法支持的浏览器如下：

*   Google Chrome 1 及以上版本
*   Edge 12 及以上
*   Firefox 1 及以上版本
*   Internet Explorer 4 及以上版本
*   Opera 4 及以上
*   Safari 1 及以上