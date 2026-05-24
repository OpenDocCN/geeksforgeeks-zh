# PERN 和 MERN 堆栈之间的差异

> 原文: [https://www.geeksforgeeks.org/difference-between-pern-and-mern-stack/](https://www.geeksforgeeks.org/difference-between-pern-and-mern-stack/)

什么是栈，如果你熟悉全栈开发，你可能会遇到 MEAN、MERN、MEVN 等术语。这些是网络栈，由用于从前端和后端构建网络应用程序的软件和框架的集合组成。您可以学习这些堆栈中的任何一个，成为全堆栈开发人员。

堆栈通常由数据库、服务器端和客户端技术以及 web 服务器组成。

## MERN STACK

MERN stack 是 `MongoDB`、`Express`、`React` Library 和 `NodeJs` 的集合。MERN 基本上是一个软件的集合，你需要创建一个动态网站和网络应用程序。

*   **M–** [`MongoDB`](https://www.geeksforgeeks.org/mongodb-an-introduction/)：是一个基于文档的无 SQL 数据库。它以类似 JSON 的文档存储数据。
*   **E–** [`Expressjs`](https://www.geeksforgeeks.org/introduction-to-express/)：是一个运行在 `NodeJS` 服务器上的服务器端框架。
*   **R–** [`React`](https://www.geeksforgeeks.org/react-js-introduction-working/)：是一个用于前端的 JavaScript 库，用于创建有吸引力的布局。
*   **N–** [`Nodejs`](https://www.geeksforgeeks.org/introduction-to-nodejs/)：是一种服务器端技术，允许你在服务器上运行 JavaScript。

从客户端到服务器端，使用的语言是 JavaScript，这使得开发人员更容易学习和开发网络应用程序。这降低了开发的成本和时间，并使开发高效。

### MERN 堆栈工作

1.  **前端的 ReactJS：** 最上面的是 `React`，这是一个用于创建动态客户端应用程序的 JS 库。我们可以将这些前端接口与后端数据连接起来。
2.  **后端的 NodeJS 和 ExpressJS：** 它允许你在服务器上使用 JavaScript，并且在 `Node` 服务器上运行 `Express`。`Express` 是一个基于 `Node.js` 的基于服务器的快速 web 框架，它处理 HTTP 请求和响应。
3.  **MongoDB 作为数据库：** 所有想要存储数据的复杂或简单的 web 应用程序都需要一个数据库。这里我们使用 `MongoDB`，它是一个 No SQL 数据库，在类似 JSON 的文档中存储数据，正如我们上面提到的。

## PERN STACK

这个堆栈由 `PostgreSQL`、`Express`、`React` 和 `Node` 组成。帮助构建全栈 web 应用程序。这个堆栈包含 `PostgreSQL` 作为数据库，而不是 `mongo` 来存储和管理数据。这是一个伟大的选择，如果你想要一个稳定的数据库，这是伟大的复杂的职责。

*   **P–** [`PostgreSQL`](https://www.geeksforgeeks.org/what-is-postgresql-introduction/)：是一个 ORDBMS（对象关系数据库管理系统）。一个基于 SQL 的数据库管理系统。
*   **E–** [`Express`](https://www.geeksforgeeks.org/introduction-to-express/)：是一个基于 `Node JS` 的服务器端框架，用于减轻服务器的任务。
*   **R–** [`React`](https://www.geeksforgeeks.org/react-js-introduction-working/)：是一个用于创建有吸引力和复杂布局的 JavaScript 库。
*   **N–** [`Nodejs`](https://www.geeksforgeeks.org/introduction-to-nodejs/)：是一种服务器端技术，允许你在服务器上运行 JavaScript。

### PERN 栈的工作

1.  **前端的 React：** 如上所述用于前端。一个帮助构建复杂用户界面的 JavaScript 库。它与服务器端技术通信。
2.  **Node 和 Express js：** `Node` 和 `Express` 在服务器端用于上述目的。
3.  **PostgreSQL 作为数据库：** 我们使用 SQL 数据库 `PostgreSQL` 代替 `MongoDB` 这样的 NoSQL 数据库。像其他 SQL 数据库一样，它以表格格式在行和列中存储数据。它有严格的数据完整性规则，比无 SQL 数据库更适合处理繁重的事务。

## PERN 与 MERN 的区别

| **MERN** | **PERN** |
| --- | --- |
| 在 MERN 中，我们使用无 SQL 数据库 (`MongoDB`)。 | 在 PERN 中，我们使用基于 SQL 的数据库 (`PostgreSQL`)。 |
| 当开发人员想要一个更快的分布式数据库时，他们会选择 `Mongo`。 | 当开发人员希望更符合 ACID 时，会使用 PERN。 |
| `PostgreSQL` 作为 SQL 数据库适合复杂的查询。 | 作为 NoSQL，`MongoDB` 不适合复杂的查询。 |
| 不适合分层数据存储。 | 最适合分层数据存储。 |