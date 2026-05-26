# MERCURIAL 和 GIT 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-mercurial-and-git/](https://www.geeksforgeeks.org/difference-between-mercurial-and-git/)

## 1. Mercurial

`Mercurial` 是一款面向软件开发人员的分布式修订控制工具，支持微软 `Windows`。`Mercurial` 是由马特·麦克于 2005 年 4 月 19 日开发的。它是一个跨平台的分布式修订工具，主要写在 `Python`、`C`、`Rust` 上，主要是一个命令行程序。所有的 `Mercurial` 操作都调用了底层驱动程序 `Hg`。`Mercurial` 支持各种操作系统，如微软 `Windows`、`UNIX-LIX` 系统（如 `FreeBSD`、`Mac OS X` 和 `Linux`）。

## 2. Git

`Git` 是一个跟踪源代码变化的分布式系统。它是由 `Linus Torvalds` 于 2005 年 4 月 7 日开发的。它支持各种操作系统，如 `Windows`、`Linux`、`MacOS`、`Solaris`。主要写在 `C`，`Perl`，`Python` 语言上。`Git` 是一个免费的开源系统，其中不需要集中式连接。它是强大而廉价的分支，易于合并。其中每个开发人员都有自己的存储库，并有一个本地副本，他们可以在其中更改历史记录。它支持具有大量代码文件的非线性开发分支和应用。

这里有一些 `.git` 目录结构：

*   `HEAD/`: 当前分支。
*   `config/`: 用于配置。
*   `description/`: 项目描述。
*   `logs/`: 记录。
*   `refs/`: 持有本地分支。

## Mercurial 和 Git 的区别

| Mercurial | Git |
| :--- | :--- |
| `Mercurial` 是软件开发人员分布式修订控制工具，它支持微软 `Windows`。 | `Git` 是一个分布式系统，它跟踪源代码的变化，每个开发人员都有自己的存储库。 |
| `Mercurial` 是由马特·麦克于 2005 年 4 月 19 日开发的。 | 它是由 `Linus Torvalds` 于 2005 年 4 月 7 日开发的。 |
| 用 `Python`，`C`，`Rust` 语言编写的 `Mercurial`。 | `Git` 用 `C`、`Perl`、`Python` 语言编写。 |
| `Mercurial` 支持 `MS Windows`，`UNIX-LIX` 系统，比如 `FreeBSD`，`Mac OS X`，和 `Linux` 操作系统。 | `Git` 支持 `Windows`、`Linux`、`MacOS`、`Solaris` 操作系统。 |
| `Mercurial` 支持 `HTTP`、`SSH` 上的自定义、电子邮件捆绑包(带有标准插件)网络协议。 | `Git` 通过 `SSH`、`Rsync`、`HTTP` 网络协议支持自定义。 |
| 默认情况下，它不允许更改其所在的版本历史。 | `Git` 允许开发者改变版本历史。 |
| `Mercurial` 提供了分支，但不如 `Git` 好。 | `Git` 提供了比 `Mercurial` 更强的分支。 |
| 与 `Git` 相比，`Mercurial` 很简单。 | `Git` 由于命令而更加复杂。 |
| `Mercurial` 不支持分段。 | `Git` 支持暂存。 |
| `Mercurial` 的特性：<br>一个理智的命令行界面。<br>更安全的 `Mercurial` 历史。<br>图形用户界面支持。<br>支持 `Windows`。<br>向后兼容。<br>易于延伸。<br>商业支持。<br>托管工具和服务。 | `Git` 的特点：<br>分布式系统。<br>分支。<br>兼容性。<br>非线性发展。<br>轻巧。<br>开源。 |