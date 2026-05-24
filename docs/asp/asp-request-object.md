# ASP 请求对象

> 原文:[https://www.geeksforgeeks.org/asp-request-object/](https://www.geeksforgeeks.org/asp-request-object/)

**ASP 请求对象**用于从客户端浏览器中检索信息。当客户端想要从服务器请求特定页面时，使用请求对象。

请求对象具有下面给出的属性、方法和集合

**集合:**

*   **Client certificate:** is used to contain all field values to be stored in the client certificate.
*   **Cookies:** Used to return all values of a set of cookies to be sent as an HTTP request.
*   **Form:** It is used to return the set of form elements published to the HTTP request body.
*   **Query string:** It is used to obtain the values of variables that will appear in the HTTP query string.
*   **Server variable:** is used to return all values of server variables.

**属性**

*   **Total Bytes:** Used to obtain the total number of bytes sent to the server through the request body.

**方法**

*   **Binary read ():** This method is used to retrieve the data sent from the client to the server by POST request. This method stores data in a secure array. Secure array is used to store information about its dimension and its bounds.

**示例:**下面的代码说明了如何返回名为“site”的 cookies 的值。a(“request . cookies”用于获取 cookie 值)

## ASP

```vb
<%
Response.Cookies("site")="GeeksforGeeks"
sitename=Request.Cookies("site")
response.write("Lets Code with " & sitename)
%>
```

**输出**

```vb
Lets code with GeeksforGeeks
```