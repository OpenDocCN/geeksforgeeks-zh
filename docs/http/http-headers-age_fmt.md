# HTTP 头：Age

> 原文：[https://www.geeksforgeeks.org/http-headers-age/](https://www.geeksforgeeks.org/http-headers-age/)

**HTTP 头 `Age`** 定义对象在代理缓存中的时间（秒）。通常，`Age` 头部的值接近于零。它由代理服务器计算，用于估算响应的当前年龄。这是一个响应头。

## 语法

```
age: <delta-seconds>
```

## 指令

此头部接受如上所述的单一指令：

*   `<delta-seconds>`：该指令定义了代理缓存中对象的非负整数秒时间单位。时间不能是负数。

## 示例

```
age: 128404
```

```
age: 1859070
```

要检查运行中的 `Age`，请转到开发者工具的 **元素 -> 网络**，检查请求头中的 `Age` 字段，如下所示，`Age` 会突出显示。

## 支持的浏览器

与 **HTTP 头 `Age`** 兼容的浏览器如下：

*   Google Chrome
*   Microsoft Edge
*   Mozilla Firefox
*   Safari
*   Opera