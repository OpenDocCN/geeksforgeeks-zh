# HTTP 头：Access-Control-Expose-Headers

> 原文：[https://www.geeksforgeeks.org/http-headers-access-control-expose-headers/](https://www.geeksforgeeks.org/http-headers-access-control-expose-headers/)

`Access-Control-Expose-Headers` 是一个响应头，用于公开其中提到的头。默认情况下，已经公开了 6 个响应头，称为 CORS 安全列表响应头。分别是：`Cache-Control`、`Content-Language`、`Content-Type`、`Expires`、`Last-Modified`、`Pragma`。

## 语法

```html
Access-Control-Expose-Headers: <header-name>
```

```html
Access-Control-Expose-Headers: *
```

**注意：** 可以使用多个头。

## 指令

*   `<header-name>`：指定要公开的头，除了 CORS 指定的安全列表头。如果有多个头在使用，我们使用逗号来分隔它们。
*   `*`（通配符）：用于没有 HTTP cookie 或 HTTP 认证信息的请求。需要注意的是，`Authorization` 头不能使用通配符，需要明确提及。

## 示例

*   在此示例中，`Accept-Language` HTTP 头被公开。可以注意到它是一个非 CORS 安全列表头。

```html
Access-Control-Expose-Headers: Accept-Language
```

*   在此示例中，`Authorization` HTTP 头需要被明确提及，因为它不能使用普通通配符。

```html
Access-Control-Expose-Headers: *, Authorization
```

## 支持的浏览器

浏览器兼容性列表如下：

**注意：** `*`（通配符）指令可能在 Safari 和 Internet Explorer 上不受支持。