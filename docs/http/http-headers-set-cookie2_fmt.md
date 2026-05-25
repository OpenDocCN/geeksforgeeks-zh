# HTTP 头 | Set-Cookie2

> 原文: [https://www.geeksforgeeks.org/http-headers-set-cookie2/](https://www.geeksforgeeks.org/http-headers-set-cookie2/)

`Set-Cookie2` 是响应类型头，已经废弃。它提供了从客户端向服务器提供和检索状态信息的机制。这个头的用法通常被 `Set-Cookie` 头代替。`Set-Cookie2` 头的用法已被 `RFC 6265` 废弃。

## 语法

```html
Set-Cookie2: <cookie-name>=<cookie-value> | Comment=<value> | Domain=<domain-value> | 
Max-Age=<non-zero-digit> | Path=<path-value> | Discard | Secure 
```

**注意:** 使用多个指令也是可以的，只需要用分号“;”分隔即可，多个Cookie之间用逗号“,”隔开。

## 指令

*   `<cookie-name>=<cookie-value>`: `<cookie-name>` 指的是Cookie的名称，而 `<cookie-value>` 指的是这个特定Cookie的值。如果名称以 `$` 开头，则不能被计算机上的任何可用应用程序使用。
*   `Comment=<value>`: 分配给 `Comment` 的 `<value>` 允许服务器记录其打算如何使用Cookie，因为Cookie用于检索或存储数据。
*   `Domain=<domain-value>`: 此指令定义发送Cookie的主机。这是一个可选指令。
*   `Path=<path-value>`: 分配给Cookie的此值指定了源服务器上应用了Cookie的所有URL集合。
*   `Max-Age=<non-zero-digit>`: 此约束的值以秒为单位，即Cookie的生命周期（秒），是一个十进制非负整数。如果此生命周期值大于增量秒数，则意味着用户应丢弃Cookie。
*   `Discard`: 此指令通过指示用户代理丢弃Cookie来删除/丢弃Cookie。一旦用户代理终止，它将被删除。
*   `Secure`: 当默认写入此约束时，Cookie将直接发送回原始服务器，没有任何偏差，以维护机密性和隐私。

## 示例

您可能在网络检查元素的标头部分找不到这种类型的Set-Cookie，因为它已被 `RFC 6265` 淘汰。请避免使用。

```html
Set-Cookie2:Student="David"; Max-Age=12885; Path="/asdf"; Secure
```

## 支持的浏览器

浏览器与 `Set-Cookie2` 头不兼容。`Set-Cookie2` 头已被 `Set-Cookie` 头取代。