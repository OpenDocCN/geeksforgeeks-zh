# NPM 脚本简介

> 原文：[https://www.geeksforgeeks.org/introduction-to-npm-scripts/](https://www.geeksforgeeks.org/introduction-to-npm-scripts/)

[NPM](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/) 是节点包管理器。它是世界上最大的软件注册中心。该注册表包含超过 800,000 个代码包。许多开源开发者使用 npm 来共享软件。许多组织也使用 npm 来管理私人开发。

“npm 脚本”是 `package.json` 文件的 `scripts` 字段中的条目。`scripts` 字段包含一个对象，您可以在其中指定要公开的各种命令和脚本。这些可以使用以下命令执行：

```
npm run <script-name>
```

NPM 脚本被用来自动完成缩小 CSS、丑化 JavaScript、构建项目等任务。NPM 脚本功能多样且简单，通过学习更少的工具，我们可以在网络项目中自动完成任务。

例如，这是我们的 `package.json` 文件。

```json
{
  "name": "example",
  "scripts": {
    "test": "echo 'hello world'"
  }
}
```

并且可以使用以下命令运行它：

```
npm run test
```

当我们有重复的任务并且必须自动化它们时，这非常有用。

## NPM 脚本内调用另一个 NPM 脚本

```json
{
  "name": "example",
  "scripts": {
    "start": "npm run lite",
    "lite": "lite-server" 
  }
}
```

所以通过使用 `npm start`，它将运行另一个命令 `npm run lite`，`lite` 是 `lite-server` 的别名。所以运行的命令是 `npm run lite-server`，这将导致节点服务器运行。

Web 开发和部署需要大量重复的任务，因此需要自动化这些任务的工具。

这里有一些可以自动化的任务。

### CSS 任务

*   编译 SAS 或 less 为 CSS。
*   运行 Autoprefixer 以添加所需的供应商前缀。
*   压缩：从源代码中删除不必要的字符（空格、换行符、注释）而不影响功能。
*   串联。

### JavaScript 任务

*   JSHint：检查 JavaScript 代码中的错误和潜在问题（静态代码分析）。
*   串联。
*   丑化：缩小并丑化（将局部变量缩减为单个字母）。
*   再次检查错误。

### 构建项目

*   您可以构建一个包含所有文件和文件夹需求以及若干依赖项的项目。
*   使用 `npm run build` 命令。

### 图像压缩与浏览器同步

*   使用 `imagemin` 压缩图像。
*   使用 `onchange` 监听文件变化，浏览器将自动重新渲染。