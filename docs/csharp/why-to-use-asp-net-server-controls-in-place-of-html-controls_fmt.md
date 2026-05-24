# 为什么用 ASP.NET 服务器控件代替 HTML 控件？

> 原文：[https://www.geeksforgeeks.org/why-to-use-asp-net-server-controls-in-place-html-controls/](https://www.geeksforgeeks.org/why-to-use-asp-net-server-controls-in-place-of-html-controls/)

基本上，HTML 控件是客户端控件，ASP.NET 控件是服务器端控件。

我们更喜欢 ASP.NET 控件作为我们的网络控件。和 HTML 控件一样，我们不能维护数据丢失的状态，因为它不提供状态管理。在编写代码时，我们不能从文件后面的代码中访问 HTML 控件。

因此，即使客户端的执行速度很快，我们也只喜欢 [ASP](https://www.geeksforgeeks.org/asp-full-form/) .NET 是因为以上两个原因。HTML 控件甚至不支持面向对象的范式，它只有一组有限的属性和方法，而 ASP.NET 完全支持面向对象的范式，可以从文件后面的代码直接访问它，并且它有一组丰富的属性和方法。

## ASP.NET

[ASP.NET](https://www.geeksforgeeks.org/introduction-to-asp-net/) 是一个用于 Web 开发的服务器端框架，它提供了以最少代码开发企业级 Web 应用程序所需的服务。它是 .NET 框架的一部分，因此在编写 ASP.NET 代码时可以访问 .NET 框架。它具有更好的用户身份验证。它使用编译后的代码来提高应用程序的性能。[ASP.NET](https://www.geeksforgeeks.org/top-50-asp-net-interview-questions-and-answers/) 页面作为代码在服务器上运行。页面被配置为当用户单击按钮时，它将被提交到服务器。当页面刷新并提交回自身时，它将再次运行服务器代码并向用户呈现其新版本。通常，Web 窗体页面在服务器上被编译为页面对象并缓存在服务器内存中。ASP.NET 页面是页面中所有服务器端控件和事件处理代码的组合。事件处理代码写在页面后面的代码文件中，因此页面作为一个单元执行。当用户第一次请求页面时，页面被动态编译和执行。因此，无需将页面预编译到程序集中。[ASP.NET 服务器控件](https://www.geeksforgeeks.org/top-50-asp-net-interview-questions-and-answers/)由一个抽象的强类型对象模型控制。它们可以拖动到工具箱中的 .aspx 页面。此外，我们还可以包含特殊控件，例如日历控件和验证控件。

## 命名空间

我们为 Web 控件使用以下命名空间：`system.web`。服务器的设计旨在更轻松地开发工具和应用程序。创建 Web 窗体的过程现在更加高效和简单。常用的 Web 服务器控件包括 `TextBox`、`Label`、`Button`、`CheckBox`、`RadioButton` 和 `GridView`。

## 验证控件

当从用户端获取数据项时，验证数据非常重要。除了客户端，还应在服务器端进行身份验证。[验证控件](https://www.geeksforgeeks.org/top-50-asp-net-interview-questions-and-answers/)通常放置在它们正在验证的控件附近。控件在回发过程之前在客户端验证数据。验证控件放置在 Web 窗体上，然后将其 `ControlValidation` 属性设置为要验证的控件。验证摘要控件用于一次性（即在一个地方）显示所有控件的验证相关错误消息。我们甚至需要提供一个控件，例如触发回发事件的按钮。尽管验证发生在客户端，但验证过程直到请求被发回才会开始。

## 状态管理

[状态管理](https://www.geeksforgeeks.org/top-50-asp-net-interview-questions-and-answers/)是一种机制，允许您在多个对相同或不同页面的请求中维护状态和页面信息。由 ASP.NET 开发的网页基于 HTTP，这是一种无状态协议。为了克服这一限制，ASP.NET 支持多个保存数据的概念，这称为状态管理。ASP.NET 为状态管理提供了不同的选项，即客户端和服务器端。在客户端，我们使用视图状态、隐藏字段、Cookie 和查询字符串。在服务器端，我们使用应用程序、会话和数据库来存储数据。

```
if (condVar > someVal) {console.log("xxx")}
```