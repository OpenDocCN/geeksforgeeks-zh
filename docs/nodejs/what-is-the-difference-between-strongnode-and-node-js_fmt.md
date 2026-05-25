# StrongNode 和 Node.js 有什么区别？

> 原文：[https://www.geeksforgeeks.org/what-is-the-difference-between-strongnode-and-node-js/](https://www.geeksforgeeks.org/what-is-the-difference-between-strongnode-and-node-js/)

`StrongLoop Node` 是 `Node.js`、`NPM` 和 `slc` 的打包发行版。`slc` 是一个命令行实用程序和一组受支持的 `npm` 模块，带有用于构建和管理应用程序的 `StrongLoop Node`。`StrongLoop Node` 附带的一些工具和模块有 [`Express`](http://expressjs.com/)、[`Connect`](www.senchalabs.org/connect/)、[`Passport`](https://www.passportjs.org/)、[`mongoose`](https://mongoosejs.com/)、[`Q`](https://github.com/kriskowal/q)、[`Request`](https://github.com/kriskowal/q)、[`Socket.IO`](https://socket.io/)。`StrongLoop` 成立于 2012 年。它的联合创始人是 `Node.js` 的核心贡献者，目前被 `IBM` 收购。

`StrongNode` 提供命令行工具，例如：

*   以命令行模式启动 `Node Inspector` 调试器。
*   创建一个随我们发行版打包的示例应用程序。
*   在我们的移动后端（即服务框架 [`loopback`](https://www.geeksforgeeks.org/node-js-frameworks/)）上创建应用程序。
*   运行标准 `npm` 和 `Node` 命令的能力。

`Node.js` 是 `Ryan Dahl` 创建的开源运行时环境。它是一个跨平台的运行时环境，用于在浏览器之外执行 `JavaScript` 代码。`PayPal`、`Uber`、`Netflix`、`Walmart` 等大公司在生产中使用 `Node.js`。

## StrongNode 与 Node.js 的区别

| StrongLoop Node | Node.js |
| --- | --- |
| `StrongLoop` 于 2013 年推出。它提供了一个开源企业版的 `Node.js`。 | `Node.js` 由 `Ryan Dahl` 于 2009 年推出。 |
| `StrongLoopNode` 是 `Node.js` 和 `NPM` 的打包发行版。 | 它是一个使用 `JavaScript` 在服务器端的运行时服务器环境。 |
| 在 `SLC` 中，我们可以为我们的 `Node.js` 应用程序构建、监控和提供移动后端。 | 但在 `Node.js` 中，我们可能需要使用一些应用程序监控工具，例如 `PM2`、`Retrace`。 |
| `StrongLoop Node` 使用 `Node.js`。 | `Node.js` 构建于谷歌的 `Chrome V8` 引擎之上。 |
| 它属于 `MIT` 开源和 `StrongLoop License` 许可。 | 它由 `MIT` 开源软件许可。 |