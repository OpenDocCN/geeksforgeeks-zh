# ASP expireasubsolute 属性

> 原文:[https://www.geeksforgeeks.org/asp-expiresabsolute-property/](https://www.geeksforgeeks.org/asp-expiresabsolute-property/)

**ASP expireasubsolute 属性**用于设置缓存在浏览器上的页面过期的日期和时间。如果用户在该日期和时间之前返回了相同的页面，则显示缓存版本。

**重要提示:**如果没有设置时间，页面会在当天午夜到期。如果未设置日期，页面将在脚本运行当天的给定时间过期。

**语法:**

```vb
response.ExpiresAbsolute[=[date][time]] 

```

**参数值:**该属性包含两个值，如上所述，如下所述:

*   **Date:** Specify the date when the cached page expires.
*   **Time:** Specifies the time when the cached page expires from the browser.

**示例:**下面的代码说明该页面将于 2020 年 3 月 23 日下午 2:00 过期。

## HTML

```vb
// setting the date and time 
<% response.ExpiresAbsolute=#March 23,2020 14:00:00# %>
```