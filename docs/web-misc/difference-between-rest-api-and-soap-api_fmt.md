# REST API 和 SOAP API 的区别

> 原文：[https://www.geeksforgeks.org/difference-between-rest-api-and-soap-api/](https://www.geeksforgeks.org/difference-between-rest-api-and-soap-api/)

SOAP 和 REST APIs 之间没有直接的比较。但是下面列出的几点可以让你在这两种网络服务中做出更好的选择。

## 以下是：

*   SOAP 代表 `S`imple `O`bject `A`ccess `P`rotocol，而 REST 代表 `RE`presentational `S`tate `T`ransfer。
*   因为 SOAP 是一个协议，它遵循严格的标准来允许客户端和服务器之间的通信，而 REST 是一种架构风格，不遵循任何严格标准，但遵循 Roy Fielding 在 2000 年定义的六个约束。这些约束是：统一接口、客户端-服务器、无状态、可缓存、分层系统和按需编码。
*   SOAP 仅使用 XML 在其消息格式中交换信息，而 REST 不限于特定的媒体类型，其实现者可以选择使用 XML、JSON 和纯文本等。并且 REST 可以使用 SOAP 协议，但 SOAP 不能使用 REST。
*   对于代表业务逻辑的服务接口，SOAP 使用 `@WebService`，而 REST 使用像 `@Path` 这样的 URI 而不是接口。
*   SOAP 难以实现且需要更多带宽，而 REST 易于实现且需要更少带宽，例如在智能手机上。
*   SOAP 相对于 REST 的优势在于 SOAP 具有 `ACID` 兼容的事务。一些应用程序需要事务处理能力，这被 SOAP 所支持，但在 REST 中缺乏。
*   在安全基础上，SOAP 具有 SSL（`S`ecure `S`ockets `L`ayer）和 WS-security，而 REST 具有 SSL 和 HTTPS。如果是银行账户密码、卡号等，SOAP 优于 REST。安全问题完全与你的应用程序需求相关，你必须构建自己的安全性。这与你使用的协议类型有关。