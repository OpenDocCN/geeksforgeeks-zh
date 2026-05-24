# HTTP 头|内容-范围

> 原文:[https://www.geeksforgeeks.org/http-headers-content-range/](https://www.geeksforgeeks.org/http-headers-content-range/)

**内容范围** HTTP 头是一个响应头，它指示部分消息在全身消息中属于哪个位置。该报头与部分实体主体一起发送，以指定部分主体应该应用于整个实体主体中的什么位置。

**语法:**

```html
Content-Range: <unit> <range-start>-<range-end>/<size>
```

```html
Content-Range: <unit> <range-start>-<range-end>/*
```

```html
Content-Range: <unit> */<size>
```

**指令:**

*   **< Unit: >:** This specifies the unit of the content range. This value is usually in bytes.
*   **< Range-Start >:** An integer that specifies the start of the request range in a given unit.
*   **< Range-End >:** An integer that specifies the end of the request range in a given unit.
*   **< Size >:** This specifies the total size of the document. Use' *' when the value is unknown.

**例:**

```html
Content-Range: bytes 500-1000/65989
```

它将范围的单位指定为字节，并将范围的起始字节指定为 500 字节，而范围的结束字节指定为 1000 字节。文档的总大小为 65989 字节。

```html
Content-Range: bytes 50-1000/*
```

它将范围的单位指定为字节，并将范围的起始字节指定为 50 字节，而范围的结束字节指定为 1000 字节。文档的总大小未知。

**支持的浏览器**以下浏览器兼容**HTTP Content-Range**: