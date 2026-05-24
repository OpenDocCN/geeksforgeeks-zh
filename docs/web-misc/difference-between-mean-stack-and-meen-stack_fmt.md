# MEAN Stack与MEEN Stack的差异

> 原文：[https://www.geeksforgeeks.org/difference-between-mean-stack-and-meen-stack/](https://www.geeksforgeeks.org/difference-between-mean-stack-and-meen-stack/)

## 什么是技术栈？

什么是栈，如果你熟悉全栈开发，你可能会遇到术语 **MEAN**，**MERN**，**MEVN**，**MEEN** 等。这些是网络栈，由用于从前端和后端构建网络应用程序的软件和框架的集合组成。您可以学习这些堆栈中的任何一个，成为全堆栈开发人员。

堆栈通常由数据库、服务器端和客户端技术以及 web 服务器组成。

### MEAN Stack

MEAN Stack 是 `MongoDB`、`Express`、`Angular` 框架和 `NodeJs` 的集合。MEAN 基本上是有助于开发全栈网络应用程序的技术集合。

*   **M – `MongoDB`** – 它是一个无 SQL 的、基于文档的数据库管理系统。它以类似 JSON 的文档存储数据。
*   **E – `ExpressJS`** – 它是一个基于 `NodeJS` 的服务器端框架。
*   **A – `AngularJS`** – 是一个用于创建动态 Web 应用程序的 JavaScript 前端框架。
*   **N – `NodeJs`** – 它是一种服务器端技术，允许你在浏览器之外运行 JS。基于 V8 引擎构建。

从前端到后端都使用了 JavaScript，因此开发人员开发全栈 Web 应用程序变得更加容易。这使得开发更加高效和快速。

### MEAN Stack 工作原理

**用于前端的 `AngularJS`** – 这是一个 JavaScript 框架，允许你使用 HTML 作为模板语言并创建动态的交互式网页，它处理用户与网络浏览器的交互，并且位于该层的顶部。

**用于后端的 `NodeJS` 和 `ExpressJS`** – `Express` 是基于 `Node` 的后端框架，运行在 `Node` 上，它处理 HTTP 请求和响应，还处理 URL 路由。

**`Mongo` 作为数据库** – 为了存储数据，我们需要一个数据库，在 MEAN 中，我们使用 `MongoDB`，这是一个无 SQL 数据库，将数据存储在类似 JSON 的文档中，还用于根据客户端需求获取数据和进行操作。

### MEEN Stack

这个栈由 `MongoDB`、`Express`、`Ember` 和 `Node` 组成。用于开发全栈网络应用程序。这个堆栈包含 `PostgreSQL` 作为数据库，而不是 `MongoDB` 来存储和管理数据。如果你想要一个稳定的数据库来处理复杂的职责，这是一个伟大的选择。

*   **M – `MongoDB`** – 它是一个无 SQL 的、基于文档的数据库管理系统。它以类似 JSON 的文档存储数据。
*   **E – `EmberJS`** – 这是一个开源的 JavaScript 客户端框架。
*   **E – `Express`** – 它是一个基于 `Node JS` 的服务器端框架，用于减轻服务器端的任务。
*   **N – `NodeJS`** – 它是一种服务器端技术，允许你在服务器上运行 JavaScript。

### MEEN Stack 工作原理

**前端 `Ember`** – 这是一个客户端框架。它提供了新的绑定语法，因为它使用了 `HtmlBars` 模板引擎。另一个引擎 `Glimmer` 渲染引擎有助于提高渲染速度。用于创建可重用的 JavaScript Web 应用程序。它由 Yehuda Katz 开发，于 2011 年 12 月 8 日首次发布。

**服务器端的 `Node` 和 `ExpressJS`** – `Node` 和 `Express JS` 在服务器端用于上述目的。

**用于数据库的 `MongoDB`** – 当在数据库中存储数据时，MEEN 栈使用 SQL 数据库 `PostgreSQL`，而不是无 SQL 数据库 `MongoDB`。它像其他 SQL 数据库一样，以表格格式在行和列中存储数据。它有严格的数据完整性规则，比无 SQL 数据库更适合繁重的事务。

### MEAN Stack与MEEN Stack的差异

| **MEAN Stack** | **MEEN Stack** |
| --- | --- |
| 在前端层的 MEAN 栈中，我们使用了 `Angular JS` 框架。 | 在前端层的 MEEN 堆栈中，我们使用了 `Ember JS` 框架。 |
| 它具有基于组件的体系结构。 | 它遵循 MVVM 架构（Model-View-ViewModel）。 |
| 它使用 `MongoDB` 作为数据库。 | 它使用 `PostgreSQL` 作为数据库。 |