# ASP 会话 LCID 物业

> 原文:[https://www.geeksforgeeks.org/asp-session-lcid-property/](https://www.geeksforgeeks.org/asp-session-lcid-property/)

**ASP 会话 LCID 属性**用于设置或获取将要发送到浏览器的页面的区域设置标识符。它设置或返回一个整数，该整数指定将根据区域位置显示的区域的位置或区域内容，如日期、时间和货币。它也被称为本地标识符属性。

**语法:**

```vb
Session.LCID(=LCID) 
```

**参数值:**

*   ***localeid:*** It contains an integer value representing locale identifier.

**示例:**下面的代码演示了本地标识符的使用。

## ASP

```vb
<%
response.write("
<p>")
response.write("Default LCID is: " & Session.LCID & "<br>")
response.write("Date format is: " & date() & "<br>")
response.write("Currency format is: " & FormatCurrency(100))
response.write("</p>
") 
%>
```

***输出:***

```vb
***Default LCID is: 2048***
***Date format is: 12/11/2001***
***Currency format is: $100.0*** 
```