# ASP 响应对象

> 原文:[https://www.geeksforgeeks.org/asp-response-object/](https://www.geeksforgeeks.org/asp-response-object/)

**响应对象是**，用于从服务器发送对客户端请求的响应。它有许多预定义的方法、属性和集合。

它有一些方法、属性和集合。

**属性**

*   **Buffer:** Defines whether to buffer the page.
*   **Cache Control:** Used to set whether the proxy server can cache HTML output.
*   **Character set:** Used to append the name of the character set to the content type header of the Response object.
*   **Content Type:** Used to set the HTTP content type/subtype of the response header object. The default value is text /HTML
*   **Expiration:** is used to set the duration of expiration before the page is displayed on the browser.
*   **Expires Absolute:** Used to set the date and time when the page cached in the browser expires.
*   **is the client certificate:** is used to specify whether the client is connected or disconnected from the server.
*   **pics:** is used to add a value to the pics tag response header.
*   **Status:** is used to specify the status value of the asp page returned by the user.

**方法**

*   **Add Header:** This method is used to specify a new name for the HTTP header and provide a given value for the HTTP response.
*   **Appendix:** This method is used to add a string to the end of the server log entry for this request.
*   **Clear:** This method is used to clear or erase the buffered HTML output.
*   **End:** This method is used to ensure that the web server stops processing scripts and returns the current results.
*   **Refresh:** This method is used to immediately send the buffered output.
*   **Redirect:** This method is used to redirect the client to a different URL.
*   **Write:** This method writes the specified string to the output.

**收藏**

*   **Cookie:** Used to set or obtain the value of cookies.

**示例:**下面的代码说明了响应对象的不同方法。

## ASP

```vb
<%
    Response.Redirect "https://www.geeksforgeeks.org" 
    Response.AppendToLog "My log message"
    Response.Write("Hello GeeksforGeeks");

    Response.AddHeader "WARNING","Error"404 Not found"

%>
```

**输出**

```vb
GeeksforGeeks
```