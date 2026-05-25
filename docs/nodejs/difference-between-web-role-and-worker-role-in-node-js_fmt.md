# node.js 中 Web 角色和工作者角色的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-web-role-and-worker-role-in-node-js/](https://www.geeksforgeeks.org/difference-between-web-role-and-worker-role-in-node-js/)

**Web 角色:** Web 角色是 `Azure` 中的云服务角色，它被定制为运行由 `IIIS` (互联网信息服务)支持的编程语言开发的基于 `Web` 的应用程序，就像我们有 `Node JS` 一样。

**工作者角色:** 工作者角色是 `Azure` 中的任何角色，它被定制为与 `Web` 角色一起在后台服务流程中运行应用程序，以频繁完成服务级别任务。

`Web` 角色和 `Worker` 角色都是与在 `port 80` 上的 `Azure` 云服务上运行应用程序相关的角色。这两种服务可以在同一个 `Azure` 实例上以相同的方式进行管理和部署。

## Web 角色与 worker 角色的区别

两种角色的主要区别在于角色在虚拟机 (`VMs`) 上的托管方式，就像 `Web` 服务器通过 `IIS` 托管应用程序，而 `Worker` 角色独立运行应用程序一样。

| **Web 角色** | **Worker 角色** |
| :--- | :--- |
| `Web` 角色是 `Azure` 中的云服务角色。 | `Azure` 中任何运行应用程序并执行特定任务的角色都可以是 `worker` 角色。 |
| 它适用于运行基于 `IIIS` 支持的编程语言的网络应用程序。 | 适用于运行应用程序和服务级别任务。 |
| `Web` 角色通过 `IIS` 自动部署和托管应用程序。 | 独立运行您的应用程序，无需 `IIS`。 |
| 主要作用是轻松创建基于 `Web` 的应用程序。 | 用于与 `Web` 角色一起执行后台支持进程。 |
| 默认安装 `IIS`。 | 默认不安装 `IIS`。 |
| 对于一些复杂的应用程序，来自用户的传入请求可以由 `Web` 角色处理。 | 对于一些复杂的应用程序，传入请求会被传递给 `job` 角色进行处理。 |