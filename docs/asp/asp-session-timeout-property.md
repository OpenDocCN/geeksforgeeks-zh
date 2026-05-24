# ASP 会话超时属性

> 原文:[https://www.geeksforgeeks.org/asp-session-timeout-property/](https://www.geeksforgeeks.org/asp-session-timeout-property/)

***ASP 会话。超时属性*** 用于设置或返回应用程序中会话的超时时间间隔。默认超时时间为 20 分钟。如果用户在超时期限内没有刷新并且没有发送任何页面请求，会话将自动结束。

***句法***

```vb
***Session.Timeout[=nMinutes]*** 
```

***属性值:***

*   ***n minutes*** : specify the number of minutes that the session will remain idle.

***例:***

```vb
***<%***
***response.write("<p>")***
***response.write("The initial Timeout is: " & Session.Timeout)***
***response.write("</p>")***

***Session.Timeout=35***

***response.write("<p>")***
***response.write("Now the Timeout is set to  now: " & Session.Timeout)***
***response.write("</p>")***
***%>***

```

**输出:**

```vb
***Initial  Timeout is: 20***
***Now the Timeout is set to: 35***
```