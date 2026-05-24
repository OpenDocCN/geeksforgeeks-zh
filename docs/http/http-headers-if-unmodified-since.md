# HTTP 头|如果-未修改-自

起

> 原文:[https://www . geesforgeks . org/http-headers-if-未修改-自/](https://www.geeksforgeeks.org/http-headers-if-unmodified-since/) 起

**HTTP If-Unmodified-由于**头是一个请求类型的头，并使请求以具有最后修改的时间戳为条件。只有在指定日期后请求的源未被修改，服务器才会执行请求的操作。如果所请求的源已被修改，则服务器将不会执行所请求的操作，并以 **412 错误(先决条件失败)**进行响应。

让我们考虑一个场景，一个病人去医学实验室做身体质量指数测试。实验室服务员记录他的身高和体重，并告诉他在 2 天内收集报告。由于某些原因，病人无法收集报告，一个月后去了实验室。但是实验室服务员没有给他报告，并告诉他，只有当他的体重仍然没有变化(或没有改变)时，测试才有效，否则，结果就变得不一致了。这就是我们的如果-未修改-因为 HTTP 头是如何工作的。

**语法:**

```html
If-Unmodified-Since: <day-name>, <day> <month> <year>
<hour>:<minute>:<second> GMT 
```

**指令:****HTTP If-未修改-自**头接受以下描述的指令:

*   **< Day name >:** It contains day names such as Monday and Tuesday. (case sensitive).
*   **< Date >:** It contains two-digit dates, such as "04" or "23" for days.
*   **< Month >:** It contains the name of the month, such as "Jan" and "Feb" in the three-letter month name. (case sensitive).
*   **< Year >:** It contains something like "2009"
*   **< Hour >:** It includes the hour in two-digit hours like "07" or "12".
*   **< Minutes >:** Same hour minutes. Two-digit minutes like "09" or "55"
*   **< Seconds >:** The image of "08" or "50" with seconds in 2 digits is included.
*   **Greenwich Mean Time:** All dates in HTTP will be displayed in Greenwich Mean Time format instead of local time format.

**示例:**

*   在通知服务器它自 2004 年 2 月 10 日(星期五)以来没有被修改的标题下面，提到的时间是 06:20:00，如果是这样，那么客户端的请求将继续。

```html
If-Unmodified-Since: Fri, 10 Feb 2004 06:20:00 GMT
```

**注意:**这样可以减少带宽使用，提高你网站的速度。

**支持的浏览器:**浏览器兼容**HTTP If-未修改-由于**头文件如下: