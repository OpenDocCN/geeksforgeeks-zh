# HTTP 头|访问控制-公开-头

> 原文:[https://www . geesforgeks . org/http-headers-access-control-expose-headers/](https://www.geeksforgeeks.org/http-headers-access-control-expose-headers/)

HTTP **访问控制-公开-头**头是一个响应头，用于公开其中提到的头。默认情况下，已经公开了 6 个响应头，称为 CORS 安全列表响应头。分别是-缓存-控制、[内容-语言](https://www.geeksforgeeks.org/http-headers-content-language/)、[内容-类型](https://www.geeksforgeeks.org/http-headers-content-type/)、过期、[上次修改](https://www.geeksforgeeks.org/http-headers-last-modified/)、Pragma。

**语法:**

```html
Access-Control-Expose-Headers: <header-name>
```

```html
Access-Control-Expose-Headers: *
```

**注意:**可以使用多个表头。

**指令:**

*   **< Header-Name >:** Specify the header to be exposed except the safety tag header specified by CORS. If there are multiple titles in use, we use commas to separate them.
*   *** (wildcard):** Used for requests without HTTP cookies or HTTP authentication information. It should be noted that the authorization header cannot be a wildcard and needs to be mentioned explicitly.

**示例:**

*   In this example, the Accept-Language HTTP header is exposed. It can be noted that it is a non-CORS safe listing title.

    ```html
    Access-Control-Expose-Headers: Accept-Language
    ```

*   In this example, the authorization HTTP header needs to be mentioned explicitly, because it can't be a normal wildcard.

    ```html
    Access-Control-Expose-Headers: *, Authorization
    ```

**支持的浏览器:**浏览器兼容 **HTTP 头访问-控制-公开-头**列表如下:

**注意:** *(通配符)指令可能在 Safari 和 Internet Explorer 上不受支持。