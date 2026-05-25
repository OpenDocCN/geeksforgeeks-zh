# HTTP 头：Content-Range

> 原文：[https://www.geeksforgeeks.org/http-headers-content-range/](https://www.geeksforgeeks.org/http-headers-content-range/)

`Content-Range` HTTP 头是一个响应头，它指示部分消息在全身消息中属于哪个位置。该报头与部分实体主体一起发送，以指定部分主体应该应用于整个实体主体中的什么位置。

## 语法

```
Content-Range: <unit> <range-start>-<range-end>/<size>
```

```
Content-Range: <unit> <range-start>-<range-end>/*
```

```
Content-Range: <unit> */<size>
```

## 指令

*   `<unit>`：指定内容范围的单位。此值通常以字节为单位。
*   `<range-start>`：一个整数，指定给定单位中请求范围的开始。
*   `<range-end>`：一个整数，指定给定单位中请求范围的结束。
*   `<size>`：指定文档的总大小。当值未知时使用 `*`。

## 例

```
Content-Range: bytes 500-1000/65989
```

它将范围的单位指定为字节，并将范围的起始字节指定为 500 字节，而范围的结束字节指定为 1000 字节。文档的总大小为 65989 字节。

```
Content-Range: bytes 50-1000/*
```

它将范围的单位指定为字节，并将范围的起始字节指定为 50 字节，而范围的结束字节指定为 1000 字节。文档的总大小未知。

## 支持的浏览器

以下浏览器兼容 `HTTP Content-Range`：