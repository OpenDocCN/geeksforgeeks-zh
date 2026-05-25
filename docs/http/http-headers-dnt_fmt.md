# HTTP 标头 | DNT

> 原文: [https://www.geeksforgeeks.org/http-headers-dnt/](https://www.geeksforgeeks.org/http-headers-dnt/)

`HTTP DNT` 头是一个请求头，允许用户选择他们的活动是否可以被他们通过 HTTP 通信的每个服务器和网络应用程序跟踪。生成的标题字段是一种允许用户选择加入或退出跟踪的机制。跟踪允许用户在网络上体验个性化内容。选择退出追踪是随着用户对隐私需求的增长而产生的。

只有当用户启用了跟踪首选项时，才能设置该头。如果用户未启用跟踪首选项，则不允许用户代理显示跟踪首选项表达式。

## 语法:

```
DNT:0
DNT:1
```

## 指令:

如果跟踪首选项设置为启用：

*   **1:** 为 HTTP DNT 头字段生成以下字段值：此指令表示目标站点禁止跟踪用户。
*   **0:** 此指令表示用户允许在给定目标站点上进行跟踪，或者用户已批准例外。

## 注意:

`DNT` 报头字段可以有零个或多个扩展名。扩展由用户代理决定。如果定义了扩展名但未设置跟踪首选项，则可以在没有字段值的情况下插入 `DNT` 标头字段。

## 示例:

*   这是一个 W3C (万维网联盟) 的示例，其中 `DNT` 头被设置为字段值 `1`：

```
GET /something/here HTTP/1.1
Host: example.com
DNT: 1
```

*   可以使用 JavaScript 的 `navigator.doNotTrack` 属性来检查 `DNT` 头字段的值。

```
console.log(navigator.doNotTrack);
// prints "1" if DNT is enabled; "0"
// if the user opted-in for tracking;
// prints "null" if unspecified
```

1.  Safari 7.1.3+、Edge、IE11 及后续版本使用 `window.doNotTrack` 而非 `navigator.doNotTrack`。
2.  在 Firefox 32 之前，`navigator.doNotTrack` 报告的是 `yes` 和 `no` 值，而不是 `1` 和 `0`。

## 支持的浏览器:

以下列出支持 `HTTP DNT` 头文件的浏览器：

*   谷歌 Chrome
*   Internet Explorer
*   微软 Edge
*   火狐
*   Opera