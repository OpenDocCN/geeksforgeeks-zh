# ASP 锁定()方法

> 原文:[https://www.geeksforgeeks.org/asp-lock-methods/](https://www.geeksforgeeks.org/asp-lock-methods/)

**ASP 锁定()方法**用于阻止其他客户端更改存储在应用程序对象中的变量。此方法用于确保一次只有一个客户端可以更改其应用程序变量。

**语法:**

```vb
Application.Lock
```

**参数值:**此方法不包含任何值。

**返回值:**没有返回值。

**示例:**下面的代码说明了 Lock 方法一次阻止多个客户端访问变量 NumVisits。

> 本申请页面已被
> 次访问！%= >
> 
> %>%@>