# ASP 请求。查询铃声收藏

> 原文:[https://www . geesforgeks . org/ASP-request-query string-collection/](https://www.geeksforgeeks.org/asp-request-querystring-collection/)

**ASP 请求。查询字符串集合**用于从网址获取将存储在 **HTTP 查询字符串**中的变量值。

**查询字符串**是以问号(？).一般包含用户的信息。

*T2？txt =这是一个查询字符串测试“>链接一个查询字符串</一个>*

**语法**

```vb
Request.QueryString(variable)[(index)|.Count] 
```

**参数值:**

*   ***Variable*** **:** is a required attribute. It defines the name of the variable in the HTTP query string.
*   ***Index:** is an optional parameter.* Define one of multiple values of a variable. Requests from **1** to **vary. QueryString (variable).**

计数

**示例:**下面的 ASP 代码从下面的请求查询字符串中返回变量的所有值。

**发出如下请求:**

```vb
***https://www.GeeksForGeeks.org/sudo/geeks.asp?x=Manas&x=Sushant***
```

## Geeks.asp

```vb
<%
for i=1 to Request.QueryString("x").Count
  Response.Write(Request.QueryString("x")(i) & "<br>")
next
%>
```

**输出**

```vb
Manas
Sushant
```