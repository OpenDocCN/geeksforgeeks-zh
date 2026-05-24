# ASP 服务器脚本超时属性

> 原文:[https://www . geesforgeks . org/ASP-server-script time out-property/](https://www.geeksforgeeks.org/asp-server-scripttimeout-property/)

***ASP 服务器脚本超时属性*** 是用来设置或返回脚本终止前的最长执行时间。

**语法:**

```vb
Server.ScriptTimeout[=NumSeconds] 
```

***参数值:***

*   ***millisecond:*** It defines the maximum number of seconds that the script can run before terminating.

**示例:**下面的代码，用于设置和返回脚本超时属性。

## ASP

```vb
<%
<!-- Set -->
Server.ScriptTimeout=50
<!-- Return -->
Response.Write(Server.ScriptTimeout)
%>
```

**输出:**

```vb
50
```