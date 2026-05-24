# ASP 解锁方式

> 原文:[https://www.geeksforgeeks.org/asp-unlock-method/](https://www.geeksforgeeks.org/asp-unlock-method/)

**ASP 解锁方法**用于在应用对象被锁定后，允许其他用户更改存储在应用对象中的变量。如果未显式调用 Unlock 方法，服务器将在脚本结束或超时时解锁锁定的应用程序对象。

***语法:***

```vb
Application.Unlock
```

**参数值:**此方法不包含任何值。

**返回值:**没有返回值。

**示例:**下方代码解锁安全。

```vb
<%
Application.Lock
Application("visits")=Application("visits")+1
Application.Unlock
%> 
```