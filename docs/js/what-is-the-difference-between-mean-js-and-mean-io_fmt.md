# MEAN.js 和 MEAN.io 有什么区别？

> 原文：[https://www.geeksforgeeks.org/what-is-the-difference-between-mean-js-and-mean-io/](https://www.geeksforgeeks.org/what-is-the-difference-between-mean-js-and-mean-io/)

**MEAN**（`MongoDB`、`Express.js`、`AngularJS`（或 `Angular`）和 `Node.js`）是一个免费的开源软件栈，用于构建动态网站和 Web 应用程序。2013 年，瓦列里·卡尔波夫（Valeri Karpov）在一篇博客文章中第一次介绍这个术语时，给出了首字母缩写 MEAN。该框架使用 `JavaScript` 进行客户端和服务器端交互。该框架经常与传统的 `LAMP` 框架（`Linux`、`Apache`、`MySQL` 和 `PHP`）进行比较。随着 `Angular` 版本的广泛流行，MEAN 栈在开发者中变得广泛流行，尤其是在美国和南亚次大陆。

## Mean.io 和 Mean.js

以色列软件开发商 Amos Haviv 第一个注意到，他为客户做的大部分项目都涉及到使用类似的技术和框架。后来，他问社区里的其他开发商，他们对这个问题是否有同样的感受，并得到了积极的回应。那是他想出 `Mean.io` 的时候，`Mean.js` 简直就是从 `Mean.io` 最初的思想里 fork 出来的一个东西，它是基于使用四种技术的核心思想：`MongoDB` 作为数据库，`Node.js` 和 `Express` 作为后端框架，`AngularJS` 作为前端框架。考虑到这一关键点，他开始构建样板代码来帮助启动这类项目。Haviv 和一家名为 Linnovate 的公司一起开源了这个样板。因为目标的不同，Haviv 离开后开始了他自己的一个新项目，名为 `Mean.js`。

## 区别

### 构建系统

| 字段 | MEAN.io | MEAN.js |
| :--- | :--- | :--- |
| 构建工具 | 它使用 `Gulp` 作为构建系统。`Gulp` 是一个开源的 `JavaScript` 工具包，在前端 Web 开发中用作流式构建系统。 | 它使用 `Grunt` 作为构建系统。`Grunt` 是一个 `JavaScript` 任务运行器，一个用于自动执行频繁任务（如压缩、编译、单元测试和代码检查）的工具。 |
| 模块结构 | `Mean.io` 更像是一个用于客户端-服务器交互的独立 `Node` 包。 | 在 `Mean.js` 中，`Angular` 在前端与 `Express` 连接进行交互。 |
| 社区支持 | 社区支持基本停滞。 | 有大量的社区支持，并且因其流行度而不断增长。 |
| 文档记录 | 关于 `Mean.io` 的文档相对较少。 | 得益于社区的支持，它拥有解释详尽的文档。 |
| 社区 | 与 `MEAN.js` 相比，`MEAN.io` 拥有更广泛的社区。 | 社区较小，但正变得越来越受欢迎，并建立了一个强大的社区。 |

近几年来，`Mean.js` 的受欢迎程度已经远远超过了 `Mean.io`。由于 `Mean.js` 和 `Mean.io` 是同一棵树的分支，开发者可以根据不同的原因选择这两个栈。作为一名开发人员，上述差异并没有那么重要，对生产团队来说更是如此。