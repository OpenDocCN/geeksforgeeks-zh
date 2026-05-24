# ASP请求查询字符串集合

> 原文：[https://www.geeksforgeeks.org/asp-request-querystring-collection/](https://www.geeksforgeeks.org/asp-request-querystring-collection/)

`ASP`请求查询字符串集合用于从网址获取将存储在`HTTP`查询字符串中的变量值。

查询字符串是以问号（`?`）开始的字符串部分，一般包含用户的信息。

[链接一个查询字符串](https://www.geeksforgeeks.org/sudo/geeks.asp?txt=这是一个查询字符串测试)

## 语法

```vb
Request.QueryString(variable)[(index)|.Count]
```

## 参数值

*   `variable`：必需属性。定义`HTTP`查询字符串中变量的名称。
*   `index`：可选参数。定义变量的多个值之一。请求范围从`1`到`Request.QueryString(variable).Count`。

## 示例

下面的`ASP`代码从下面的请求查询字符串中返回变量的所有值。

**发出如下请求：**

```vb
https://www.GeeksForGeeks.org/sudo/geeks.asp?x=Manas&x=Sushant
```

### Geeks.asp

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