# HTTP头：If-Unmodified-Since

> 原文：[https://www.geeksforgeeks.org/http-headers-if-unmodified-since/](https://www.geeksforgeeks.org/http-headers-if-unmodified-since/)

**HTTP If-Unmodified-Since** 头是一个请求类型的头，并使请求以具有最后修改的时间戳为条件。只有在指定日期后请求的源未被修改，服务器才会执行请求的操作。如果所请求的源已被修改，则服务器将不会执行所请求的操作，并以 `412 Precondition Failed` 错误进行响应。

让我们考虑一个场景，一个病人去医学实验室做身体质量指数测试。实验室服务员记录他的身高和体重，并告诉他在 2 天内收集报告。由于某些原因，病人无法收集报告，一个月后去了实验室。但是实验室服务员没有给他报告，并告诉他，只有当他的体重仍然没有变化(或没有改变)时，测试才有效，否则，结果就变得不一致了。这就是 `If-Unmodified-Since` HTTP 头是如何工作的。

## 语法

```
If-Unmodified-Since: <day-name>, <day> <month> <year> <hour>:<minute>:<second> GMT
```

## 指令

`If-Unmodified-Since` 头接受以下描述的指令：

### `<day-name>`
它包含星期名称，例如 Monday 和 Tuesday。（区分大小写）。

### `<day>`
它包含两位数的日期，例如 "04" 或 "23"。

### `<month>`
它包含月份的名称，例如三字母月份名称 "Jan" 和 "Feb"。（区分大小写）。

### `<year>`
它包含类似 "2009" 的年份。

### `<hour>`
它包含两位数的小时，例如 "07" 或 "12"。

### `<minute>`
与小时对应的分钟。两位数的分钟，例如 "09" 或 "55"。

### `<second>`
与分钟对应的秒数。两位数的秒数，例如 "08" 或 "50"。

### `GMT`
HTTP 中的所有日期都将以格林尼治标准时间格式显示，而不是本地时间格式。

## 示例

在通知服务器它自 2004 年 2 月 10 日(星期五)以来没有被修改的标题下面，提到的时间是 06:20:00，如果是这样，那么客户端的请求将继续。

```
If-Unmodified-Since: Fri, 10 Feb 2004 06:20:00 GMT
```

**注意：** 这样可以减少带宽使用，提高你网站的速度。

## 支持的浏览器

浏览器兼容 `If-Unmodified-Since` 头文件如下：