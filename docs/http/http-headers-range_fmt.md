# HTTP Range 头

> 原文: [https://www.geeksforgeeks.org/http-headers-range/](https://www.geeksforgeeks.org/http-headers-range/)

HTTP 头用于通过 HTTP 请求或响应传递附加信息。`HTTP Range` 是一个 HTTP 请求头，用于从服务器获取文档的一部分。如果服务器返回文档的该部分，它将使用 `206` (部分内容)状态代码。如果范围无效，使用的状态代码是 `416` (范围不可满足)，服务器使用状态代码 `200` (正常)，以防它忽略范围请求。

## 语法

*   从特定范围获取整个文档

```
Range: <unit>=<range-start>-
```

*   请求多个部分

```
Range: <unit>=<range-start>-<range-end>, <range-start>-<range-end>
```

*   请求文档的特定结尾部分

```
Range: <unit>=-<suffix-length>
```

## 指令

`HTTP Range` 头接受的指令有四个，上面提到了，下面描述:

*   `Unit`: 指定给定范围的单位。通常使用 `bytes`。
*   `Range-Start`: 是一个整数，指定文档部分的开始。
*   `Range-End`: 是一个整数，指定文档部分的结束。这是一个可选指令。
*   `suffix-length`: 是一个整数，指示要返回的文档结尾部分的长度。

## 示例

*   获取文件的前 100 字节

```
Range: bytes=0-99
```

*   获取文件的最后 100 字节

```
Range: bytes=-100
```

*   多个请求范围

```
Range: bytes=0-99, 700-799
```

要检查该范围是否有效，请转到检查 **元素 -> 网络** 检查范围的请求标题。

## 支持的浏览器

以下列出了 `HTTP Range` 头支持的浏览器: